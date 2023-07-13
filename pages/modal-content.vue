<template>
    <div>
        <!-- モーダルウィンドウのトリガーボタン -->
        <button @click="showModal">モーダルを開く</button>

        <!-- モーダルウィンドウのコンテンツ -->
        <div v-if="isOpen" class="modal">
            <div class="modal-content">
                <!-- モーダルウィンドウの内容 -->
                <h2>モーダルウィンドウ</h2>
                <p>モーダルウィンドウの内容をここに記述します。</p>

                <!-- モーダルウィンドウを閉じるボタン -->
                <button @click="hideModal">閉じる</button>
            </div>
        </div>
    </div>
</template>
  
<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
    data() {
        return {
            isOpen: ref(false), // モーダルウィンドウの表示状態を管理するリアクティブなフラグ
        };
    },
    methods: {
        showModal() {
            this.isOpen = true; // モーダルウィンドウを表示する
        },
        hideModal() {
            this.isOpen = false; // モーダルウィンドウを非表示にする
        },
    },
});
</script>
  
<style>
.modal {
    /* モーダルウィンドウのスタイルを定義 */
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
}

.modal-content {
    /* モーダルウィンドウのコンテンツスタイルを定義 */
    background-color: #fff;
    padding: 20px;
    border-radius: 4px;
}
</style>
  