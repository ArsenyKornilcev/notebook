<template>
	<header>
		<h1>{{ headerCaption }}</h1>
	</header>
</template>

<script>
export default {
	name: "TheHeader",
	props: ["headerCaption"],
};
</script>

<style scoped>
header {
	width: 100%;
	height: 100%;
	display: flex;
	justify-content: center;
	align-items: center;
	background: #002c8a;
}
header h1 {
	color: #fff;
	margin: 0;
	font-size: 3rem;
}
</style>
