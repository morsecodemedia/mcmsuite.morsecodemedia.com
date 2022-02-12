<template>
  <div>
    <h1>
      The MCM Suite of Tools
    </h1>
    <p>Doing the minimal amount of thinking so you can do even less.</p>
    <section v-if="tools">
      <article
        v-for="(tool, index) in sortedTools(tools)"
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
      </article>
    </section>
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
          name: 'Color Palette',
          description: 'An accessibility color contrast checker for all variations of a seven color, color palette. Basically the Color Contrast Checker on steroids.',
          url: 'https://color-palette.morsecodemedia.com',
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
  methods: {
    sortedTools: (arr) => {
      return arr.slice().sort((a, b) => (a.name > b.name) ? 1 : (a.name === b.name) ? ((a.url > b.url) ? 1 : -1) : -1)
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

<style lang="scss">
h1 {
  font-size: 40px;
  margin-bottom: 20px;
}

h2 {
  font-size: 34px;
  margin-bottom: 20px;
}

p {
  font-size: 24px;
  line-height: 1.4;
  margin-bottom: 15px;
}

a {
  background: black;
  border: 1px solid black;
  border-radius: 10px;
  color: white;
  display: inline-block;
  font-size: 20px;
  padding: 15px 25px;
  text-decoration: none;
  &:hover {
    background: white;
    color: black;
    text-decoration: none;
  }
  &:focus {
    background: white;
    color: black;
    text-decoration: none;
    outline: 2px dotted black;
  }
}

#main {
  max-width: 750px;
  margin: 0 auto;
  padding: 15px 5%;
}

article {
  border-top: 1px solid lightgrey;
  padding: 35px 0;
  height: 100%;
  min-height: moz-available;
  max-height: 80vh;
  display: block;
}
</style>
