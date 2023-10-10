<template>
    <b-container class="pt-4">
        <b-row>
            <b-col class="col-6 col-md-5 col-lg-4 pe-0">
                <PrimaryNavigation />
                <AllChatList @updateChat="updateChat" />
            </b-col>
            <b-col class="col-6 col-md-7 col-lg-8 ps-0">
                <ChatWindow :selectedUser="selectedUserChat" />
            </b-col>
        </b-row>
    </b-container>
</template>

<script>
import PrimaryNavigation from '@/components/PrimaryNavigation.vue'
import AllChatList from '@/components/AllChatList.vue'
import ChatWindow from '@/components/ChatWindow.vue'
export default {
    name: 'App',
    page: {
        title: "Whatsapp",
        meta: [{ name: "description", content: "Document Log" }],
    },
    components: {
        PrimaryNavigation,
        AllChatList,
        ChatWindow
    },
    data() {
        return {
            selectedUserChat:null,
        }
    },
    methods: {
        updateChat(user) {
            this.selectedUserChat = user
        }
    }
}
</script>