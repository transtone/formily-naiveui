<template>
  <FormProvider :form="form">
    <SchemaField>
      <SchemaStringField
        name="time"
        title="时间"
        required
        x-decorator="FormItem"
        x-component="TimePicker"
        :x-component-props="{
          style: {
            width: '240px',
          },
        }"
      />
    </SchemaField>
    <Submit @submit="log"> 提交 </Submit>
  </FormProvider>
</template>

<script lang="ts" setup>
import { createForm } from '@formily/core'
import { createSchemaField, FormProvider } from '@formily/vue'
import { FormItem, TimePicker, Submit } from '@formily/naive-ui'

const form = createForm()
const { SchemaField, SchemaStringField } = createSchemaField({
  components: {
    FormItem,
    TimePicker,
  },
})

const log = (value) => {
  console.log(value)
}
</script>
