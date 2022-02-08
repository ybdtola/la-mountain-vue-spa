<template>
    <div class="wrapper">
        <button @click="toggleAccordion()">
            <slot name="title"></slot>
        </button>
        <div v-show="isOpen">
            <slot name="content"></slot>
        </div>
    </div>
</template>
<script>
    export default{
        data() {
    return {
      isOpen: false,
    };
  },

  methods: {
    toggleAccordion() {
      this.isOpen = !this.isOpen;
    },
  },
};
    
</script>
<style lang="scss" scoped>
    .wrapper{
        max-width: 425px;
            button{
                font-family: 'Oswald';
                font-size: 20px;
                font-weight: 700;
                width: 100%;
                border: none;
                outline: none;
                cursor: pointer;
                background: #414f6b;
                color: #b0b4be;
                padding: 5px 20px;
                text-align: left;
                height: 50px;
                &:hover{
                     background: #b0b4be;
                    color: #414f6b;
                    text-decoration: underline;
                }
            }
}
</style>
