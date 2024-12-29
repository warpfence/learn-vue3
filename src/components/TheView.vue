<template>
	<main>
		<div class="container py-4">
			<PostCreate @create-post="createPost"></PostCreate>
			<hr class="my-4" />

			<div class="row g-3">
				<div v-for="post in posts" :key="post.id" class="col col-4">
					<AppCard
						:title="post.title"
						:contents="post.contents"
						:type="post.type"
						:is-like="post.isLike"
						@toggle-like="post.isLike = !post.isLike"
					></AppCard>
				</div>
			</div>
			<hr class="my-4" />
			<!-- :model-value="username" @update:model-value="value => (username = value)" -->
			<LabelInput v-model="username" label="이름"></LabelInput>
			<Username
				v-model:firstname="firstname"
				v-model:lastname="lastname"
			></Username>
		</div>
	</main>
</template>

<script>
import AppCard from '@/components/AppCard.vue';
import PostCreate from '@/components/PostCreate.vue';
import LabelInput from '@/components/LabelInput.vue';
import Username from '@/components/Username.vue';

import { reactive, ref } from 'vue';
export default {
	components: {
		AppCard,
		PostCreate,
		LabelInput,
		Username,
	},
	setup() {
		const posts = reactive([
			{
				id: 1,
				title: '제목1',
				contents: '내용1',
				type: 'news',
				isLike: true,
			},
			{ id: 2, title: '제목2', contents: '내용2', type: 'news', isLike: true },
			{ id: 3, title: '제목3', contents: '내용3', type: 'news', isLike: true },
			{ id: 4, title: '제목4', contents: '내용4', type: 'news', isLike: true },
			{
				id: 5,
				title: '제목5',
				contents: '내용5',
				type: 'notice',
				isLike: false,
			},
			{
				id: 6,
				title: '제목6',
				contents: '내용6',
				type: 'notice',
				isLike: false,
			},
		]);

		const createPost = newPost => {
			console.log('newPost: ', newPost);
			posts.push(newPost);
		};

		const username = ref('');
		const firstname = ref('');
		const lastname = ref('');
		return { posts, createPost, username, firstname, lastname };
	},
};
</script>

<style lang="scss" scoped></style>
