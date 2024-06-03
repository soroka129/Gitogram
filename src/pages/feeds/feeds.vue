<template>
    <div class="topline">
        <topline>
            <template #headline>
                <div class="icon">
                    <icon name="home"/>
                </div>
            </template>
            <template #content>
                <ul class="stories">
                    <li class="stories-item" v-for="story in stories" :key="story.id">
                        <story-user-item :avatar="story.avatar" :username="story.username" @onPress="handlePress(story.id)" />
                    </li>
                </ul>
            </template>
        </topline>
        <feed />
    </div>
</template>

<script>
import { topline } from '../../components/topline'
import { storyUserItem } from '../../components/storyUserItem'
import { icon } from '../../icons'
import stories from './data.json'
import { feed } from '../../components/feed'

export default {
  name: 'feeds',
  components: {
    topline,
    storyUserItem,
    icon,
    feed
  },
  data () {
    return {
      stories
    }
  }
}
</script>

<style lang="scss" scoped src="./feeds.scss"></style>
