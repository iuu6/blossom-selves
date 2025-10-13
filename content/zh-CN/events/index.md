---
title: 活动日历
layout: page
events:
  "暂无活动":
    time: 2025-02-28T18:30:00-05:00
    lang:
      - 普通话
      - English
    community:
      - 暂无活动
    link:
      type: 预约报名
      url: https://example.com
    image: expressivearts-compressed.jpg
---

<div class="EventGrid">
  <div class="container">
    <div class="events">
      <div v-for="(item, name) in $frontmatter.events" :key="name" class="event" loading='lazy'>
        <div class="date" v-if="item.time">
          <span class="year">{{ (new Date(item.time)).toLocaleDateString('default', {  year: 'numeric' }) }}</span>
          <span class="month">{{ (new Date(item.time)).toLocaleDateString('default', {  month: 'short' }) }}</span>
          <span class="day">{{ (new Date(item.time)).toLocaleDateString('default', { day: 'numeric' }) }}</span>
          <div class="actual-date">
            <span class="year">{{ (new Date(item.time)).toLocaleDateString('default', {  year: 'numeric' }) }}</span>
            <span class="month">{{ (new Date(item.time)).toLocaleDateString('default', {  month: 'short' }) }}</span>
            <span class="day">{{ (new Date(item.time)).toLocaleDateString('default', { day: 'numeric' }) }}</span>
          </div>
        </div>
        <div>
          <div class="info">
            <div class="summary"> {{ name }} </div>
            <div class="time">
              <span v-if="item.time">
                {{ (new Date(item.time)).toLocaleTimeString('default', { weekday: "long", hour: '2-digit', minute: '2-digit', hour12: false, timeZoneName: "short" }) }}
              </span>
              <span v-if="item.location">
                @ {{ item.location }}
              </span>
            </div>
            <div class="community">
              <div v-for="c in item.community" :key="c" class="cclick" loading='lazy'> {{ c }}
              </div>
              <div class="clink" v-if="item.link && item.link.type">
                <a v-if="item.link && item.link.type" class="link-type" :href="`${item.link.url}`">
                  {{ item.link.type }}
                </a>
              </div>
            </div>
            <!--div class="lang">
                {{
                item.lang
                ? item.lang.reduce((x, y) => x + " / " + y)
                : "English / 普通话 / 吳語 / 日本語"
                }}
                </div-->
          </div>
          <div class="poster">
            <img :src="`/assets/events/${item.image}`" :alt="`${name}`" />
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<style scoped lang="sass">
// vitepress/VPFeatures
.EventGrid
    position: relative
    padding: 0 24px

@media (min-width: 640px)
    .EventGrid
        padding: 0 48px

@media (min-width: 960px)
    .EventGrid
        padding: 0 64px

// See Also: ../Calendar.vue

$grid__cols: 12
.container
    margin: 0 auto
    max-width: 1152px

.events
    display: block
    width: 100%
    padding: 1em 0 1em 0

// Event box (this card style is copied from VitePress homepage theme)
.event
    display: flex
    gap: 1em
    border: 1px solid var(--vp-c-bg-soft)
    border-radius: 12px
    height: 100%
    background-color: var(--vp-c-bg-soft)
    transition: border-color 0.25s, background-color 0.25s
    padding: 1em
    margin: 0 0 1em 0
    width: 100%

@media (min-width: 960px)
    .events
        display: block
        column-count: 2

.event:hover
    border-color: var(--vp-c-brand-1)

img
    border-radius: 12px

.date, .actual-date
    display: flex
    gap: 0.5em
    justify-content: flex-end

.date
    .month, .day, .year
        font-size: 1.5em

    .dow
        font-size: 1.2em
        line-height: 1.2em

    // BEGIN sideways-lr COMPATIBILITY WORKAROUND
    // It's okay if you don't understand this whole ordeal, css is awesome right?
    // Check https://stackoverflow.com/q/77353660/7346633
    writing-mode: vertical-rl
    position: relative

    span
        opacity: 0

    .actual-date
        position: absolute
        top: 0
        left: 0

        writing-mode: lr
        width: max-content
        transform: rotate(-90deg) translateX(-100%)
        transform-origin: top left

        span
            opacity: unset
    // END sideways-lr COMPATIBILITY WORKAROUND

.dow, .time, .month
    color: var(--vp-c-brand-1)

.summary
    font-weight: bold
    font-size: 1.2em
    margin: 0 0 4px 0

.description
    margin-top: 1em

.community
    display: flex
    gap: 6px
    flex-wrap: wrap
    padding: 6px 0px 6px 0px
    margin: 0 0 4px 0

.cclick, .clink
    border: 1px solid var(--vp-c-indigo-soft)
    border-radius: 12px
    padding: 2px 8px 0 8px
    color: var(--vp-c-indigo-1)
    background-color: var(--vp-c-indigo-soft)
    height: 26px
    white-space: nowrap

.clink
    border: 1px solid
    border-radius: 12px
    padding: 2px 8px 0 8px
    color: var(--vp-c-red-1)
    background-color: var(--vp-c-red-soft)

// Phone
@media(max-width: 600px)
    .event
        flex-direction: column
        gap: 1.5em
        font-size: 0.8em

    .date
        writing-mode: horizontal-tb
        transform: none
        justify-content: flex-start
        align-items: flex-end

        .actual-date
            display: none

        span
            opacity: 1

</style>
