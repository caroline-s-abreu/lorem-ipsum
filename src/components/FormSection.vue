<template>
  <div class="form-section fixed-form">
    <h2>
      Lorem Ipsum is simply <span>dummy text</span> of the printing and typesetting
      <span>industry</span>.
    </h2>
    <form @submit.prevent="handleSubmit">
      <div class="form-inputs">
        <div class="form-group">
          <label for="name">Nome</label>
          <input
            type="text"
            id="name"
            placeholder="Digite seu nome"
            v-model="formData.name"
            required
          />
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input
            type="email"
            id="email"
            placeholder="exemplo@mail.com.br"
            v-model="formData.email"
            required
          />
        </div>
        <div class="form-group">
          <label for="phone">Telefone</label>
          <input
            type="tel"
            id="phone"
            placeholder="(00) 00000.0000"
            v-model="formData.phone"
            required
          />
        </div>
        <div class="form-group">
          <label class="select" for="option">Como prefere ser contatado?</label>
          <select
            id="option"
            v-model="formData.option"
            :class="{ placeholder: formData.option === '' }"
            required
          >
            <option disabled value="">Selecione a melhor opção</option>
          </select>
        </div>
      </div>
      <div class="form-footer">
        <div class="form-radios">
          <div class="form-radio">
            <input id="radio1" type="radio" required />
            <label for="radio1">Lorem Ipsum is simply dummy</label>
          </div>
          <div class="form-radio">
            <input id="radio2" type="radio" required />
            <label for="radio2">Lorem Ipsum is simply dummy</label>
          </div>
        </div>
        <button type="submit">Enviar</button>
      </div>
    </form>
    <div class="whatsapp">
      <img src="../assets/whatsapp.svg" alt="whastapp icon" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'FormSection',
  setup() {
    const formData = ref({
      name: '',
      email: '',
      phone: '',
      option: ''
    })

    const handleSubmit = () => {
      console.log('Form Data:', formData.value)
    }

    return { formData, handleSubmit }
  }
})
</script>

<style scoped lang="scss">
.form-section {
  background-color: white;
  padding: 70px 12px;
  box-shadow: 0px 8px 32px 0px #5757571a;
  border-radius: 4px;
  max-width: 1295px;

  h2 {
    text-align: center;
    font-size: 28px;
    color: #810059;
    font-weight: 400;
    padding: 0 6px;
    margin-bottom: 20px;

    span {
      font-weight: 700;
    }
  }

  form {
    display: flex;
    flex-direction: column;
    gap: 20px;

    .form-inputs {
      display: flex;
      flex-direction: column;
      gap: 20px;

      .form-group {
        display: flex;
        flex-direction: column;
        gap: 4px;
        padding: 0 18px;

        label {
          text-align: start;
          font-weight: 400;
          font-size: 12px;
          color: #292929;
        }

        input,
        select {
          border: 1px solid #b0bec580;
          border-radius: 4px;
          padding: 14px 19px;

          &::placeholder {
            font-size: 16px;
            font-weight: 400;
            color: #78909c;
          }
        }

        select {
          background-color: #fff;

          option[value=''] {
            color: #78909c;
          }
        }
        select.placeholder {
          font-size: 16px;
          font-weight: 400;
          color: #78909c;
        }
      }
    }

    .form-footer {
      display: flex;
      flex-direction: column;
      gap: 20px;
      align-items: center;

      .form-radios {
        display: flex;
        flex-direction: column;
        gap: 20px;
        align-items: center;

        .form-radio {
          display: flex;
          gap: 12px;
          align-items: center;
          justify-content: center;
          padding: 0 40px;

          label {
            font-size: 13px;
            font-weight: 400;
            color: #292929;
          }

          input[type='radio'] {
            accent-color: #ff7f00;
          }
        }
      }

      button {
        background-color: #f57c00;
        border: none;
        color: white;
        cursor: pointer;
        padding: 18px 120px;
        border-radius: 8px;
        font-size: 20px;
        transition: background-color 0.3s ease;
        text-align: center;

        &:hover {
          background-color: #e67100;
        }
      }
    }
  }

  .whatsapp {
    display: none;
  }
}

@media (min-width: 1024px) {
  .fixed-form {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    margin: 0 auto;
    width: 100%;
    z-index: 1000;
    max-width: 1295px;
    padding: 32px;
    box-shadow: 0px 8px 32px 0px #5757571a;

    h2 {
      span {
        font-weight: 400;
      }
    }

    form {
      .form-inputs {
        .form-group {
          input {
            padding: 14px 40px 14px 14px;
          }

          select {
            padding: 14px 32px 14px 14px;
          }
        }
      }

      .form-inputs,
      .form-footer {
        flex-direction: row;
        justify-content: space-between;
      }

      .form-footer {
        .form-radios {
          flex-direction: row;
          justify-content: space-between;

          .form-radio {
            padding: 0 18px;
          }
        }

        button {
          margin-right: 18px;
        }
      }
    }

    .whatsapp {
      display: flex;
      position: absolute;
      top: -109px;
      right: 20px;
      z-index: 1001;
      padding: 15px;
      background-color: #25d366;
      border-radius: 50%;
    }
  }
}
</style>
