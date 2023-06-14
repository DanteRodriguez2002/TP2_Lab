<script setup>

</script>

<template>
    <section class="container mt-5">
        <div class="card card-rounded p-3">

            <div class="card-body">
                <div class="row">
                    <div class="col-2">
                        <img src="../assets/profile-photo.jpg" alt="" class="profile-photo" width="200" height="200">
                    </div>
                    <div class="col-6">
                        <h1 class="card-title"><b>Jane Doe</b></h1>
                        <p class="card-text"><b>Email:</b> jane_doe@email.com</p>
                        <p class="card-text"><b>Fecha de nacimiento:</b> 01/05/1996</p>
                        <p class="card-text"><b>Telefono:</b> 918-936-9585</p>
                        <p class="card-text"><b>Ciudad:</b> Tokyo, Japon</p>
                        <p class="text-secondary">Trabajando en <b>Lawn N</b></p>
                    </div>
                    <div class="col-4">
                        <div class="d-flex align-items-end justify-content-end btn-follow">
                            <button type="button" class="btn btn-primary" id="btn-follow"
                                @click="followUnfollow(like.flagFollow)" v-if="like.flagFollow">Seguir</button>
                            <button v-else type="button" class="btn btn-danger" @click="followUnfollow(like.flagFollow)">No
                                seguir</button>

                        </div>

                    </div>
                </div>


            </div>
        </div>
    </section>
</template>
<script>

export default {
    name: 'ProfileCard',


    methods: {
        followUnfollow: function (flag) {
            console.log(flag)
            if (flag) {
                this.like.flagFollow = false
            } else {
                this.like.flagFollow = true
            }

        },


    },
    data: function () {
        return {
            like: {
                flagFollow: true,
                likes: 0
            },
            comments: {
                name: "",
                text: "",
            },
        }
    }
}
</script>