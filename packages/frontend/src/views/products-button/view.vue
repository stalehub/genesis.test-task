<script setup lang="ts">
  import LoaderSmIcon from "../loader-icon/loader-icon.vue";

  interface Props {
  text:String,
    disabled:Boolean,
    loading:Boolean
  }

  const {loading,text,disabled} = defineProps<Props>()

</script>

<template>
    <div class="my-button-wrapper">
        <button class="my-button" :disabled="disabled || loading" @onclick="$emit('click')">
            <LoaderSmIcon v-if="loading"/>
            <span v-else>{{text}}</span>
        </button>
    </div>
</template>

<style scoped>
    .my-button{
        display: block;
        position: relative;
        overflow: hidden;
        text-decoration: none;
        text-transform: uppercase;
        letter-spacing: 2px;
        color: white;
        font-size: 0.9rem;
        font-weight: 500;
        text-align: center;
        padding: 12px 10px;
        border-radius: 5px;
        background: var(--primary);
        background: linear-gradient(90deg, var(--primary) 20%, var(--secondary) 75%);
        border: none;
        outline: none;
        width: 80px;
        cursor: pointer;
        transition: background 3s;
    }
    .my-button:not(:disabled):hover{
        background: linear-gradient(90deg, var(--primary) 50%, var(--secondary) 90%);
        transition: background 3s;
    }
    .my-button:disabled{
        cursor: not-allowed;
        opacity: 0.5;
    }
</style>
