<template>
  <div class="wrapper">
    <a
      v-if="banner && banner.image"
      :href="`${banner.url}?utm_source=CTA&utm_medium=content-text&utm_campaign=${id}-03`"
      class="link"
      target="banner"
    >
      <picture v-if="banner.image">
        <source
          type="image/webp"
          :srcset="`${banner.image.url}?w=300&fm=webp, ${banner.image.url}?w=600&fm=webp 2x`"
        />
        <img :src="banner.image.url" class="image lazyload" :alt="banner.alt" />
      </picture>
    </a>
  </div>
</template>

<script>
export default {
  props: {
    banner: {
      type: Object,
      required: false,
      default: undefined,
    },
    id: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.image {
  width: 300px;
  border-radius: 5px;
}

.link {
  display: block;
  margin-bottom: 40px;
}

@media (max-width: 1160px) {
  .wrapper {
    text-align: center;
  }
}
</style>
