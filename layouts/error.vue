<template>
  <div class="relative">
    <nui-container v-if="error.statusCode === 404" class="pt-20">
      <div class="flex flex-wrap items-center justify-between">
        <h1 class="w-full text-3xl xl:text-4xl light:text-light-onSurfacePrimary dark:text-dark-onSurfacePrimary text-center font-medium leading-normal -mb-6 z-10">
          {{ error.message }}
        </h1>
        <div class="w-full lg:w-2/3 mx-auto">
          <lost-image/>
        </div>
      </div>
    </nui-container>
    <nui-container v-else class="flex flex-wrap items-center justify-between pt-20 lg:pt-0">
      <div class="w-full lg:w-1/2 text-center lg:text-left pl-8">
        <h1 class="text-6xl font-medium leading-normal text-nuxt-lightgreen">
          {{ error.statusCode }}
        </h1>
        <h3 class="text-4xl light:text-light-onSurfacePrimary dark:text-dark-onSurfacePrimary font-medium leading-relaxed mb-6">
          {{ error.message }}
        </h3>
      </div>
      <div class="hidden lg:block lg:w-5/12 xl:w-4/12">
        <mountains-globe />
      </div>
    </nui-container>
  </div>
</template>

<script>
import mountainsGlobe from '@/components/svg/streamline/montains-globe'
import lostImage from '@/components/svg/fogg/404'

export default {
  components: {
    mountainsGlobe,
    lostImage
  },
  props: {
    error: {
      type: Object,
      required: true
    }
  }
}
</script>
