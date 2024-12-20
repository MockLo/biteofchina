<script setup>
import { NForm, NFormItem, NInput, NButton, useMessage } from 'naive-ui';

const message = useMessage();
const formRef = ref(null);
const formValue = ref({
  productName: '',
  location: '',
  description: '',
  price: '',
  category: '',
  images: [''],
});
const rules = {
  productName: {
    required: true,
    message: 'Please enter the product name',
    trigger: 'blur',
  },
  location: {
    required: true,
    message: 'Please enter the location',
    trigger: 'blur',
  },
  description: {
    required: true,
    message: 'Please enter the description',
    trigger: 'blur',
  },
  price: {
    required: true,
    message: 'Please enter the price',
    trigger: 'blur',
  },
};

const handleSubmit = e => {
  e.preventDefault();
  formRef.value?.validate(errors => {
    if (!errors) {
      // TODO:
    } else {
      message.error('Please check the form');
    }
  });
};
</script>

<template>
  <main class="page">
    <section class="section">
      <h1 class="title">Publish Your Travel Product</h1>

      <NForm ref="formRef" size="large" class="my-form" :model="formValue" :rules="rules">
        <NFormItem label="Product Name" path="productName">
          <NInput v-model:value="formValue.productName" placeholder="Enter product name" />
        </NFormItem>

        <NFormItem label="Location" path="location">
          <NInput v-model:value="formValue.location" placeholder="Enter city name" />
        </NFormItem>

        <NFormItem label="Description" path="description">
          <NInput
            v-model:value="formValue.description"
            type="textarea"
            :autosize="{
              minRows: 3,
              maxRows: 5,
            }"
            placeholder="Enter product description, as short and clear as possible"
          />
        </NFormItem>

        <NFormItem label="Price ($)" path="price">
          <NInput v-model:value="formValue.price" placeholder="Enter product price" />
        </NFormItem>

        <NFormItem label="Category" path="category">
          <NInput v-model:value="formValue.category" placeholder="Choose or customize a category" />
        </NFormItem>

        <NFormItem label="Upload Images (less than 8)" path="images">
          <NInput v-model:value="formValue.images" placeholder="Simplicity and naturalness are the best policies." />
        </NFormItem>

        <NFormItem>
          <div class="buttons">
            <NButton size="large" type="info" @click="handleSubmit">Submit</NButton>
            <!-- <NButton size="large" type="error" secondary>Clear</NButton> -->
          </div>
        </NFormItem>
      </NForm>
    </section>
  </main>
</template>

<style lang="scss" scoped>
.page {
  height: 100vh;
  overflow: hidden;
  background-color: #f3f4f6;
}

.section {
  width: 756px;
  margin: 40px auto;
  padding: 36px;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: 0px 4px 6px -4px rgba(0, 0, 0, 0.1), 0px 10px 15px -3px rgba(0, 0, 0, 0.1), 0px 0px 0px 0px #000,
    0px 0px 0px 0px #000;
}

.title {
  color: #1f2937;
  font-size: 24px;
  font-weight: 600;
}

.my-form {
  margin-top: 30px;

  :deep(.n-form-item-label) {
    color: #374151;
    font-size: 14px;
    font-weight: 700;
    line-height: 20px; /* 142.857% */
  }
}

.buttons {
  width: 100%;
  display: flex;
  /* justify-content: space-between; */
  gap: 36px;
}
</style>
