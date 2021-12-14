<template>
  <div>
    <h1>
      The MCM Suite of Tools
    </h1>
    <p>Doing the minimal amount of thinking so you can do even less.</p>
    <div v-if="tools">
      <div
        v-for="(tool, index) in tools"
        :key="index"
      >
        <h2>{{ tool.name }}</h2>
        <p>{{ tool.description }}</p>
        <a
          :href="tool.url"
          target="_blank"
        >
          Use Tool
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Homepage',
  data () {
    return {
      tools: [
        {
          name: 'Color Contrast Checker',
          description: 'An accessibility checker tool for validating the color contrast based on WCAG 2.0 and WCAG 2.1 standards.',
          url: 'https://morse.sh/ccc',
          image: ''
        },
        {
          name: 'Meta Tags',
          description: 'A page to check character count and preview meta tags in various scenarios.',
          url: 'https://morse.sh/meta',
          image: ''
        },
        {
          name: 'UTM Generator',
          description: 'A simple UTM generator.',
          url: 'https://morse.sh/utm',
          image: ''
        },
        {
          name: 'Veeva Subject Lines',
          description: 'A collaboration with James Tomasino, this tool is to test subject line lengths for use in Veeva CLM.',
          url: 'https://morse.sh/vaesubjects',
          image: ''
        },
        {
          name: 'Accessibility Learnings',
          description: 'This site is a collection of checklists, guidelines, tutorials and other information gathered while studying for my IAAP Certified Professionals Accessibility Core Competencies (CPACC) certification.',
          url: 'https://morse.sh/a11y',
          image: ''
        }
      ]
    }
  },
  head () {
    return {
      title: '',
      meta: [
        { hid: 'ogtitle', property: 'og:title', content: '' },
        { hid: 'twtitle', name: 'twitter:title', content: '' },
        { hid: 'googlename', itemprop: 'name', content: '' },
        { hid: 'description', name: 'description', content: '' },
        { hid: 'ogdescription', property: 'og:description', content: '' },
        { hid: 'twdescription', name: 'twitter:description', content: '' },
        { hid: 'googledescription', itemprop: 'description', content: '' },
        { hid: 'ogurl', property: 'og:url', content: 'https:/mcmsuite.morsecodemedia.com' + this.$route.path },
        { hid: 'twsite', name: 'twitter:site', content: 'https://mcmsuite.morsecodemedia.com' + this.$route.path }
      ],
      link: [
        { hid: 'canonical', rel: 'canonical', href: 'https://mcmsuite.morsecodemedia.com' + this.$route.path }
      ]
    }
  }
}
</script>

<style>

</style>
