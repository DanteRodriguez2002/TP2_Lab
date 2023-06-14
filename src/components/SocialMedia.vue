<script setup>
import { ref } from 'vue'

const message = ref('')
</script>
<template>
    <section class="container mt-5">
        <div class="row">
            <div class="col-8 mb-5">
                <div class="card card-rounded">
                    <div class="card-body">
                        <p class="text-secondary px-4">Publicado hace 1 semana</p>
                        <img src="../assets/feed-img.jpg" alt="" class="feed-img">
                        <div class="row px-4">
                            <div class="col">
                                <button type="button" class="btn btn-primary" id="btn-like"
                                    @click="like_dislike(like.flagLike)" v-if="like.flagLike">Me gusta</button>
                                <button v-else type="button" class="btn btn-danger" @click="like_dislike(like.flagLike)">No
                                    me gusta</button>
                            </div>
                            <div class="col">
                                <p class="text-secondary text-likes text-end"><span id="cont-likes"><b>{{ like.likes
                                }}</b></span> Likes</p>
                            </div>
                        </div>
                        <div class="mt-5 px-4">
                            <h5>Comentarios</h5>
                        </div>
                        <div class="text-box-comments px-4">
                            <!-- {{ comments.boxComment }} -->
                            <p v-for="item in boxComment" v-bind:key="item.id">{{ item.message }}</p>
                        </div>
                        <div class="row px-4 mb-4">
                            <div class="col-10">
                                <span v-if="comments.textFieldError" style="color: red;">No puedes agregar un comentario
                                    vacio</span>
                                <input type="text" class="form-control" placeholder="Deja tu comentario..."
                                    id="comment-field" v-model.trim="message">
                                <div class="error hidden"></div>
                            </div>
                            <div class="col-auto">
                                <button type="button" class="btn btn-primary" id="btn-comment"
                                    @click="add_comment(message)">Comentar</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-4">
                <div class="card card-rounded">
                    <div class="card-body">
                        <h5 class="card-title">Sobre mi</h5>
                        <p class="card-text">¡Hola a todos! Soy Jane, y actualmente vivo en la vibrante y
                            emocionante ciudad de Tokio,Japón.Me encanta capturar la
                            esencia de la vida urbana a través de mi lente,explorando
                            el constraste ente la arquitectura moderna y las tradiciones
                            centenarias que conviven en esta metrópolis única.
                            Desde rascacielos deslumbrantes y calles bulliciosas hasta
                            templos serenos y jardines tranquilos, encuentro inspiracion
                            en cada rincón de esta increíble ciudad.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

export default {
    name: 'SocialMedia',


    methods: {
        like_dislike: function (flag) {
            if (flag) {
                this.like.flagLike = false
                this.like.likes++
            } else {
                this.like.flagLike = true
                this.like.likes--
            }

        },

        add_comment: function (text) {
            if (text === '') {
                this.comments.textFieldError = true


            } else {
                this.boxComment.push({ message: text })
                this.comments.textFieldError = false

            }
        }
    },

    data: function () {
        return {
            like: {
                flagLike: true,
                likes: 0
            },
            comments: {
                name: "",
                text: "",
                textFieldError: false,
                boxComment: []
            },
            boxComment: [

            ]
        }
    }
}
</script>