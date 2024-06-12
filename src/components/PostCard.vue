<script>
export default {
    name: 'PostCard',
    props: {
        postInfo: Object
    }
}
</script>

<template>
    <div class="card my-3">
        <!-- <img src="..." class="card-img-top" alt="..."> -->
        <div class="card-body">
            <h5 class="card-title">{{ postInfo.name }}</h5>
            <div v-if="postInfo.type">
                <strong>Type</strong>:
                {{ postInfo.type.name }}
            </div>
            <p v-if="postInfo.summary" class="card-text">{{ postInfo.summary }}</p>
            <!-- <a href="#" class="btn btn-primary">Go somewhere</a> -->
        </div>
    </div>
</template>