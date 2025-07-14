<script setup>
import { reactive } from 'vue';
import UserInfo from './UserInfo.vue';
import Repository from './Repository.vue';
import Form from './Form.vue';

const state = reactive({
  login: '',
  name: '',
  bio: '',
  company: '',
  avatar_url: '',
  repos: [],
  searchInput: ''
})

async function fetchGithubUser(username) {
  const res = await fetch(`https://api.github.com/users/${username}`)
  const { login, name, bio, company, avatar_url } = await res.json()

  state.login = login
  state.name = name
  state.bio = bio
  state.company = company
  state.avatar_url = avatar_url

  fetchUserRepositories(login)
}

async function fetchUserRepositories(username) {
  const res = await fetch(`https://api.github.com/users/${username}/repos`)
  const repos = await res.json()

  state.repos = repos
}
</script>

<template>
  <slot></slot>
  <Form @form-submit="fetchGithubUser" />
  <UserInfo v-if="state.login !== ''" :login="state.login" :name="state.name" :company="state.company" :bio="state.bio" :avatar_url="state.avatar_url" />
  <section v-if="state.repos.length > 0">
    <h2>Public Repositories: {{ state.repos.length }}</h2>
    <article>
      <Repository v-for="repo of state.repos" :full_name="repo.full_name" :description="repo.description" :html_url="repo.html_url"/>
    </article>
    </section>
    <slot name="footer"></slot>
</template>