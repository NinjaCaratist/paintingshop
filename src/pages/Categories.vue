<template>
  <div class="categories">
    <div class="on-sale"
         @click="router.push('/paintings')"
    >
        <h3>В наличии</h3>
    </div>
    <div class="on-order">
      <h3>Под заказ</h3>
    </div>
    <div class="sold">
      <h3>Распроданы</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "PaintingsCategories"
}
</script>

<script setup>
import { useRouter } from "vue-router";
const router = useRouter();
</script>

<style scoped lang="sass">

.categories
  display: flex
  flex-wrap: wrap
  align-items: center
  justify-content: center

  padding: 50px 0
  //border-top: 4px solid var(--seagreen)

  div
    width: 300px
    height: 300px
    overflow: hidden
    margin-right: 30px
    border-radius: 10px

    cursor: pointer
    position: relative

    display: flex
    align-items: center
    justify-content: center

    @media screen and (max-width: 1200px)
      width: 250px
      height: 250px

    @media screen and (max-width: 800px)
      margin-bottom: 30px

    &::before
      content: ''
      display: block
      top: 0
      left: 0
      width: 100%
      height: 100%
      position: absolute
      background: rgba(128, 128, 128, 0.5)
      opacity: 100%
      transition: opacity 0.2s ease-in-out

    &:hover::before
      opacity: 0

.on-sale, .on-order, .sold
  background-size: cover

.on-sale
  background-image: url("@/assets/meadow.jpg")

.on-order
  background-image: url("@/assets/seedlings.jpg")

.sold
  background-image: url("@/assets/mountains.jpg")

h3
  z-index: 2
  color: white
  font-size: 25px
  font-weight: 300
  text-shadow: 0 0 2px #000000

</style>