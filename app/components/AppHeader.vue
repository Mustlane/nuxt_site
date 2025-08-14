<script setup lang="ts">
import type { NavigationMenuItem } from '@nuxt/ui'

const item = ref<NavigationMenuItem[]>([
  {
    label: 'Guide',
    icon: 'i-lucide-book-open',
    to: '/getting-started'
  },
  {
    label: 'Composables',
    icon: 'i-lucide-database',
    to: '/composables'
  },
  {
    label: 'Components',
    icon: 'i-lucide-box',
    to: '/components',
    active: true,
    children: [
      {
        label: 'Link',
        icon: 'i-lucide-file-text',
        description: 'Use NuxtLink with superpowers.',
        to: '/components/link'
      },
      {
        label: 'Modal',
        icon: 'i-lucide-file-text',
        description: 'Display a modal within your application.',
        to: '/components/modal'
      },
      {
        label: 'NavigationMenu',
        icon: 'i-lucide-file-text',
        description: 'Display a list of links.',
        to: '/components/navigation-menu'
      },
      {
        label: 'Pagination',
        icon: 'i-lucide-file-text',
        description: 'Display a list of pages.',
        to: '/components/pagination'
      },
      {
        label: 'Popover',
        icon: 'i-lucide-file-text',
        description: 'Display a non-modal dialog that floats around a trigger element.',
        to: '/components/popover'
      },
      {
        label: 'Progress',
        icon: 'i-lucide-file-text',
        description: 'Show a horizontal bar to indicate task progression.',
        to: '/components/progress'
      }
    ]
  }
])
</script>

<template>
  <UHeader>
    <template #left>
      <NuxtLink to="/">
        <LogoPro class="w-auto h-6 shrink-0" />
      </NuxtLink>
      <TemplateMenu />
    </template>

    <template #default>
      <UNavigationMenu
        content-orientation="vertical"
        :items="item"
        :highlight="false"
        class="w-full justify-center"
      />
    </template>

    <template #right>
      <AppSearch />
      <UChip
        size="3xl"
        :show="true"
      >
        <UButton
          icon="i-lucide-mail"
          color="neutral"
          variant="subtle"
        />
      </UChip>
      <UColorModeButton />
    </template>
  </UHeader>
</template>
