<template>
  <div>
    <main class="p-4 bg-gray-50 min-h-screen">
      <div
        class="max-w-screen-xl mx-auto bg-white p-8 rounded-lg shadow-2xl"
      >
      <h2 class="text-3xl my-6">评论</h2>
        <!-- 评论框 -->
        <CommentBox />
        <!-- 分隔线 -->
        <DividerHorizontal />
        <div v-for="comment in comments" :key="comment.id">
          <!-- 评论 -->
          <CommentItem 
            :user="comment.user"
            :avatar="comment.avatar"
            :time="comment.time"
            :content="comment.content"
          />
          <ReplyBox v-if="comment.replies">
            <!-- 回复 -->
            <CommentItem
              v-for="reply in comment.replies"
              :key="reply.id"
              :user="reply.user"
              :avatar="reply.avatar"
              :time="reply.time"
              :content="reply.content"
            />
          </ReplyBox>
        </div>
        </div>
    </main>
  </div>
</template>
<script setup lang="ts">
import CommentBox from "./components/CommentBox.vue";
import CommentItem from "./components/CommentItem.vue";
import DividerHorizontal from "./components/DividerHorizontal.vue";
import ReplyBox from "./components/ReplyBox.vue";

import face1 from "./assets/face1.png";
import face2 from "./assets/face2.png";
import face3 from "./assets/face3.png";

const comments = [
  {
    id: 1,
    user: "梦落轻寻",
    avatar: face1,
    time: "2小时之前",
    content:
      "哇！这篇文章真是写的太好啦！收到很大的启发，希望博主能够再接再厉，产出越来越多，越来越好的文章！凑字数，字数，字数...",
    replies: [
      {
        id: 2,
        user: "陌上花开",
        avatar: face2,
        time: "2小时之前",
        content: "赞！",
      },
      {
        id: 3,
        user: "半梦半醒半浮生√<",
        avatar: face3,
        time: "2小时之前",
        content:
          "这是一篇非常长的长篇大论，这篇文章写的非常好，无论是技术点还是理论点，都非常的好。而且主题分明，每一个点都有自己的解释，这篇文章的主题是：CSS3的新特性，如何使用CSS3的新特性，以及如何使用CSS3的新特性。真的是非常好的文章。",
      },
    ],
  },
];

</script>
<style lang="scss" scoped>

</style>