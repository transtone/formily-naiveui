<template>
  <FormProvider :form="form">
    <SchemaField :schema="schema" />
    <Submit @submit="onSubmit">提交</Submit>
  </FormProvider>
</template>

<script lang="ts" setup>
import { createForm } from '@formily/core'
import { createSchemaField, FormProvider } from '@formily/vue'
import { FormItem, InputNumber, Submit } from '@formily/naive-ui'

const schema = {
  type: 'object',
  properties: {
    inputNumber: {
      type: 'number',
      title: '输入框',
      'x-decorator': 'FormItem',
      'x-component': 'InputNumber',
      'x-component-props': {
        style: {
          width: '240px',
        },
      },
    },
  },
}

const form = createForm()
const { SchemaField } = createSchemaField({
  components: {
    FormItem,
    InputNumber,
  },
})

const onSubmit = (value) => {
  console.log(value)
}
</script>
