<template>
  <v-container>
    <validation-observer
      ref="observer"
      v-slot="{ invalid }"
    >
      <form @submit.prevent="submit">
        <validation-provider
          v-slot="{ errors }"
          name="お名前"
          rules="required|max:10"
        >
          <v-text-field
            v-model="name"
            :counter="10"
            :error-messages="errors"
            label="お名前（必須）"
            required
          ></v-text-field>
        </validation-provider>
        <validation-provider
          v-slot="{ errors }"
          name="メールアドレス"
          rules="required|email"
        >
          <v-text-field
            v-model="email"
            :error-messages="errors"
            label="メールアドレス（必須）"
            required
          ></v-text-field>
        </validation-provider>
        <validation-provider
          v-slot="{ errors }"
          name="ご用件"
          rules="required"
        >
          <v-select
            v-model="select"
            :items="items"
            :error-messages="errors"
            label="ご用件（必須）"
            data-vv-name="select"
            required
          ></v-select>
        </validation-provider>
        <validation-provider
          v-slot="{ errors }"
          name="件名"
        >
          <v-text-field
            v-model="subject"
            :error-messages="errors"
            label="件名（任意）"
          ></v-text-field>
        </validation-provider>
        <validation-provider
          v-slot="{ errors }"
          name="お問い合わせ内容"
          rules="required"
        >
          <v-text-field
            v-model="name"
            :error-messages="errors"
            label="お問い合わせ内容（必須）"
            required
          ></v-text-field>
        </validation-provider>

        <v-btn
          class="mr-4 mt-4"
          type="submit"
          :disabled="invalid"
        >
          送信
        </v-btn>
      </form>
    </validation-observer>

    <!-- <v-row>
      <v-col
        cols="12"
        md="4"
      >
        <v-text-field
          v-model="name"
          :rules="nameRules"
          :counter="16"
          label="お名前"
          required
        ></v-text-field>
      </v-col>
      <v-col
        cols="12"
        md="4"
      >
        <v-text-field
          v-model="email"
          :rules="emailRules"
          label="メールアドレス"
          required
        ></v-text-field>
      </v-col>
      <v-col
        cols="12"
        md="4"
      >
        <v-select
          v-model="select"
          :items="items"
          :rules="[v => !!v || 'ご用件は必須です']"
          label="ご用件"
          required
        ></v-select>
      </v-col>
    </v-row> -->
  </v-container>
</template>

<script>
import { required, email, max } from 'vee-validate/dist/rules'
import { extend, ValidationObserver, ValidationProvider, setInteractionMode } from 'vee-validate'

setInteractionMode('eager')

extend('required', {
  ...required,
  message: '{_field_} は必須です',
})

extend('max', {
  ...max,
  message: '{_field_} は {length} 文字以下にしてください',
})

extend('email', {
  ...email,
  message: '入力されたメールアドレスは無効です',
})

export default {
  components: {
    ValidationProvider,
    ValidationObserver,
  },
  data: () => ({
    name: '',
    email: '',
    select: null,
    items: [
      'ご質問',
      'ご意見',
      'ご要望',
      'その他',
    ],
  }),

  methods: {
    submit () {
      this.$refs.observer.validate()
    },
  },
}
</script>
