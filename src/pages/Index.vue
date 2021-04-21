<template>
  <Layout>
    <div class="container">
      <IndexInfo />
      <ProjectGrid :projects="$page.projects.edges" />
    </div>
    <LatestJournals :journals="$page.journals.edges" />
  </Layout>
</template>

<page-query>
query Posts {
	projects: allStrapiPosts {
    edges {
      node {
        id
        published_at (format: "YYYY")
        title
        categories
        thumbnail {
          url (quality: 90)
        }
      }
    }
  },
  journals: allStrapiAtricles (perPage: 4) {
    edges {
      node {
        id
        title
        published_at (format: "YYYY-MM-DD HH:mm:ss")
      }
    }
  }
}
</page-query>

<script>
import IndexInfo from '@/components/IndexInfo'
import ProjectGrid from '@/components/ProjectGrid'
import LatestJournals from '@/components/LatestJournals'

export default {
  name: 'IndexPage',
  components: {
    IndexInfo,
    ProjectGrid,
    LatestJournals
  }
}
</script>

<style></style>
