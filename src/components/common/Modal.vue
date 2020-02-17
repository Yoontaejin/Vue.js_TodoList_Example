<template>
    <transition name="modal">
        <div class="modal-mask">
            <h3 slot="header">
                경고 !
                <i class="closeModalBtn fas fa-times" @click="showModal=false"></i> 
            </h3>
            <div slot="body"> 아무것도 입력하지 않으셨습니다. </div> 
        </div>
    </transition>
</template>

<script>
export default {

}
</script>
<style>
</style>