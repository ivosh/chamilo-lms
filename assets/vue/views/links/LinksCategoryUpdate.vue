<template>
  <div>
    <h2 class="text-h3 font-small text-gray-800 mb-4">
      {{ t('Update category') }}
    </h2>
    <hr class="m-0 mb-4"/>
    <LinkCategoryForm
      :category-id="categoryId"
      @back-pressed="goBack"
    />
  </div>
</template>

<script setup>
import LinkCategoryForm from "../../components/links/LinkCategoryForm.vue";
import {useRoute, useRouter} from "vue-router";
import {computed} from "vue";
import {useI18n} from "vue-i18n";

const {t} = useI18n()
const router = useRouter()
const route = useRoute()

const goBack = () => {
  router.push({
    name: "LinksList",
    query: route.query,
  });
}

const categoryId = computed(() => {
  return route.params.id
})
</script>
