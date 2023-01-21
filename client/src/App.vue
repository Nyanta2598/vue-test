<script setup>
import { ref, computed } from 'vue'
import Home from './Home.vue'
import Todo from './Todo.vue'
import NotFound from './NotFound.vue'

const routes = {
  '/': Home,
  '/todo': Todo
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound
})
</script>

<template>
  <div id="pattern" class="pattern">
    <a href="#menu" class="menu-link">Menu</a>
    <nav id="menu" role="navigation">
      <ul>
        <li><a href="#/" class="menu-link">Home</a></li>
        <li><a href="#/todo" class="menu-link">Todo</a></li>
        <li><a href="#/non-existent-path" class="menu-link">Broken Link</a></li>
      </ul>
    </nav>
    <component :is="currentView" />
  </div>
</template>
<style scoped>
  a.menu-link {
    float: right;
		display: block;
		padding: 1rem;
    text-decoration: none;
  }
  a.menu-link:hover {
    text-decoration: underline;
  }
	nav[role=navigation] {
		clear: both;
		-webkit-transition: all 0.3s ease-out;  
		-moz-transition: all 0.3s ease-out;
		-ms-transition: all 0.3s ease-out;
		-o-transition: all 0.3s ease-out;
		transition: all 0.3s ease-out;
	}
	.js nav[role=navigation] {
		overflow: hidden;
		max-height: 0;
	}
	nav[role=navigation].active {
		max-height: 1em;
	}
	nav[role=navigation] ul {
		margin: 0;
		padding: 0;
		border-top: 1px solid #808080;
	}
	nav[role=navigation] li a {
		display: block;
		padding: 0.8em;
		border-bottom: 1px solid #808080;
	}
	@media screen and (min-width: 48.25em) {
		a.menu-link {
			display: none;
		}
		.js nav[role=navigation] {
			max-height: none;
		}
		nav[role=navigation] ul {
			margin: 0 0 0 -0.25em;
			border: 0;
		}
			
		nav[role=navigation]  li {
			display: inline-block;
			margin: 0 0.25em;
		}
		nav[role=navigation] li a {
			border: 0;
		}
	}
</style>