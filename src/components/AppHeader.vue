<script>
export default {
    name: 'AppHeader',
}
</script>

<template>
    <header>
        <div class="container-fluid">
            <div class="container-fluid">
                <div class="row">
                    <div class="col-12 d-flex">
                        <img src="https://upload.wikimedia.org/wikipedia/commons/1/11/Yu-Gi-Oh%21_%28Logo%29.jpg"
                            alt="Yu-Gi-Oh Main Logo" class="me-3">
                        <h1 class="py-3">Yu-Gi-Oh Api</h1>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
header {
    background-color: $white;
}
img {
    width: 90px;
    object-fit: contain;
}
</style>