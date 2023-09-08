<script setup>
import { ref, computed, watch, onMounted, onUnmounted } from 'vue'
import { AppstoreOutlined } from '@ant-design/icons-vue'
import ChocolateMenuIcon from '@/components/icons/IconChocolateMenu.vue'

// Define reactive properties
const isClicked = ref(false)
const selectedKeys = ref(['1'])
const openKeys = ref([''])
const isMenuOpen = ref(false)
const isSticky = ref(false)
const myHeader = ref(null)

// Define a mapping between the link key and the section id
const sectionIds = {
  Home: 'home',
  'About us': 'about',
  Schedule: 'schedule',
  Speakers: 'speakers',
  Sponsors: 'sponsors',
  FAQ: 'faq'
  // Add mappings for other links as needed
}

// watch sub mobile menu property
watch(isMenuOpen, (val) => {
  if (val) {
    openKeys.value = ['sub2']
  } else {
    openKeys.value = ['']
  }
})

// Computed property for button class
const buttonClass = computed(() => ({
  'register-btn': true,
  clicked: isClicked.value
}))

// Event handlers
const scaleDown = async (event) => {
  event.preventDefault()

  isClicked.value = true

  await new Promise((resolve) => {
    setTimeout(() => {
      isClicked.value = false
      resolve()
    }, 1500)
  })

  window.open(
    'https://docs.google.com/forms/d/e/1FAIpQLScKCTDITcfJCI_tROrIIsBq-uh4dqivAwua86tE6kAwP9ja8A/viewform',
    '_blank',
    'noopener noreferrer'
  )
}

const titleClick = (e) => {
  console.log('titleClick', e)
}

const handleClick = (e) => {
  console.log('click', e)
  openKeys.value = ['']

  const sectionId = sectionIds[e.key]
  if (sectionId) {
    // Calculate the offset to account for the header height
    const headerHeight = document.querySelector('header').offsetHeight

    // Use the element's `scrollIntoView` method to scroll to the section with the offset
    const sectionElement = document.getElementById(sectionId)
    if (sectionElement) {
      const scrollToY = sectionElement.offsetTop - headerHeight - 230
      console.log('Scrolling to Y:', scrollToY)

      window.scrollTo({
        top: scrollToY,
        behavior: 'smooth'
      })
    }
  }
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const handleScroll = () => {
  if (window.scrollY > myHeader.value.offsetTop) {
    isSticky.value = true
  } else {
    isSticky.value = false
  }
}

// Lifecycle hooks
onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header :class="{ 'bg-blue-theme': !isSticky, sticky: isSticky }" ref="myHeader">
    <div class="header-bg px-5 py-7">
      <div class="mx-auto flex max-w-screen-xl items-center justify-between gap-x-[5%]">
        <div class="flex items-center gap-x-3">
          <button class="md:hidden" @click="toggleMenu"><ChocolateMenuIcon /></button>
          <RouterLink to="/"
            ><img alt="Logo" src="@/assets/logo.svg" class="w-9/12 lg:w-full"
          /></RouterLink>
        </div>

        <nav class="hidden w-full max-w-screen-sm justify-between md:flex">
          <a href="#" v-scroll-to="'#hero'" class="nav-link">Home</a>
          <a href="#" v-scroll-to="'#about'" class="nav-link">About us</a>
          <a href="#" v-scroll-to="'#schedule'" class="nav-link">Schedule</a>
          <a href="#" v-scroll-to="'#speakers'" class="nav-link">Speakers</a>
          <a href="#" v-scroll-to="'#sponsors'" class="nav-link">Sponsors</a>
          <a href="#" v-scroll-to="'#faq'" class="nav-link">FAQ</a>
        </nav>

        <a href="#" :class="buttonClass" @click="scaleDown">Register now</a>
      </div>
    </div>

    <a-menu
      id="dddddd"
      v-model:openKeys="openKeys"
      v-model:selectedKeys="selectedKeys"
      mode="inline"
      @click="handleClick"
      class="antd-custom-menu"
    >
      <a-sub-menu key="sub2" @titleClick="titleClick">
        <template #icon>
          <AppstoreOutlined />
        </template>
        <template #title>Navigation Two</template>
        <a-menu-item key="Home">Home</a-menu-item>
        <a-menu-item key="About us">About us</a-menu-item>
        <a-menu-item key="Schedule">Schedule</a-menu-item>
        <a-menu-item key="Speakers">Speakers</a-menu-item>
        <a-menu-item key="Sponsors">Sponsors</a-menu-item>
        <a-menu-item key="FAQ">FAQ</a-menu-item>
      </a-sub-menu>
    </a-menu>
  </header>
</template>

<style scoped>
.header-bg {
  /* border: 3px solid linear-gradient(136deg, rgba(255, 255, 255, 0.2), rgb(255, 255, 255)); */
  /*
  */
  border: 3px solid rgba(255, 255, 255, 0.014);
  background: linear-gradient(
      175deg,
      rgba(177, 177, 177, 0.32) 5.24%,
      rgba(54, 53, 103, 0.2) 51.01%
    ),
    rgba(0, 0, 128, 0.3);
  backdrop-filter: blur(3.3px);
}
.nav-link {
  @apply font-urbanist text-xl font-medium text-white;
}

.register-btn {
  @apply flex h-[40px] w-full max-w-[165px] items-center justify-center rounded-[80px] px-9 text-sm font-extrabold text-[#121139] md:h-14 md:max-w-[196px] md:text-lg;
  background: linear-gradient(180deg, #fc711b 25.62%, #fc4608 100.89%);
}

.clicked {
  transform: scale(0.9);
}

.sticky {
  @apply fixed top-0 z-50 w-full;
}
</style>
