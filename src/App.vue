<script setup lang="ts">
let z: string | null = null;

addEventListener("click", () => {
	typeof z;
	//     ^?
	// sould be `string | null`
});

addEventListener("click", () => {
	if (typeof z === "string") return;
	typeof z;
	//     ^?
	// sould be `null`
});

addEventListener("click", () => {
	if (z === null) return;
	typeof z;
	//     ^?
	// sould be `string`
});
</script>

<template>
	{{ z }}
	<!-- should be `string | null` -->
</template>
