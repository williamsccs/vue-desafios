<template>
    <div class="container">
        <div v-if="errores.length != 0" class="alert alert-danger">
            {{ mostrarErrores }}
        </div>
        <!-- formulario -->
        <form id="formulario" action="" @submit.prevent="validarFormulario">
            <div class="row">
                <div class="col col-12">
                    <br><br>
                    <!-- nombre -->
                    <label for="inputNombre" class="text-start">Tu nombre</label>
                    <input v-model="nombre" @keyup.space="contar" type="text" class="form-control" id="inputNombre"
                        placeholder="Nombre completo">

                    <br>
                    <!-- edad -->
                    <label for="inputDNI" class="form-label text-start">DNI</label>
                    <input v-model.number="dni" type="number" class="form-control" id="inputDNI" placeholder="DNI">

                    <br>
                    <!-- email -->
                    <label for="inputEmail" class="form-label text-start">Email</label>
                    <input v-model="email" type="email" class="form-control" id="inputEmail" placeholder="tu@email.com">

                    <br>
                    <!-- Documentos radio -->
                    <div class="row">
                        <h4>Selecciona tu Sexo</h4>
                        <div class="col">
                            <input v-model="sexo" type="radio" name="checkHombre" class="form-check-input"
                                value="Hombre">
                            <label for="checkDNI">Hombre</label>
                        </div>
                        <div class="col">
                            <input v-model="sexo" type="radio" name="checkMujer" class="form-check-input" value="Mujer">
                            <label for="checkPass">Mujer</label>
                        </div>
                        <div class="col">
                            <input v-model="sexo" type="radio" name="checkOtro" class="form-check-input" value="otro">
                            <label for="checkVisa">Otro</label>
                        </div>
                        <br>
                        <!-- email -->
                        <label for="inputOtro" class="form-label text-start">Otro</label>
                        <input v-model="sexo" type="text" class="form-control" id="inputOtro"
                            placeholder="como te identificas" :disabled="disabled">

                        <br>
                    </div>
                    <hr>
                    <div class="row">
                        <br>
                        <div class="col-10"></div>
                        <br>
                        <!-- submit -->
                        <div class="col-2">
                            <input type="submit" class="btn btn-primary" value="ENVIAR">
                        </div>
                        <br>
                    </div>
                </div>
            </div>
        </form>
    </div>
</template>
  
<script>


export default {
    name: 'FormularioVue',
    data() {
        return {
            nombre: '',
            dni: '',
            email: '',
            sexo: '',
            usuarios: {},
            disabled: true,
            errores: [],
            contador: 1
        };
    },
    methods: {
        validarFormulario() {
            //event.preventDefault();
            if (this.nombre && this.contador > 1 && this.dni && this.email && this.sexo) {
                alert("Campos obligatorios están ok, enviando formulario!");

                this.usuarios = { nombre: this.nombre, dni: this.dni, email: this.email, sexo: this.sexo }
                this.enviar()


                setTimeout(() => {
                    //reset del formulario
                    document.getElementById("formulario").reset();
                    //vuelvo todas las variables a estado inicial
                    // Object.assign(this.$data.dni, this.$options.data());
                    this.nombre = ""
                    this.dni = ""
                    this.email = ""
                    this.sexo = ""
                }, 3000);
                console.log(JSON.stringify(this.usuarios))
                return true;
            }
            if (!this.nombre) {
                this.errores.push("El nombre es obligatorio. ");
            }
            if (this.contador < 2) {
                this.errores.push("El nombre debe estar compuesto por nombre y apellido! ")
            }
            if (!this.dni) {
                this.errores.push("el DNI es campo obligatorio. ");
            }
            if (!this.email) {
                this.errores.push("El email es obligatorio. ");
            }
            if (!this.sexo) {
                this.errores.push("El Genero es obligatorio. ");
            }
            setTimeout(() => {
                this.errores = [];
            }, 3000);
        },
        contar() {
            console.log("Agregando otro nombre");
            this.contador++;
        },
        enviar() {
            this.$emit("enviar", this.usuarios);
        }
    },
    computed: {
        mostrarErrores() {
            let misErrores = this.errores.join(" ");
            return misErrores;
        },
        isDisabled() {
            return this.form.validated;
        }

    },
    watch: {
        sexo(sexo) {
            if (sexo === "otro") {
                this.disabled = false

            }
            if (sexo === "Hombre" || sexo === "Mujer") {
                this.disabled = true
            }


        }
    }

}
</script>
  
<style scoped>
a {
    color: #42b983;
}

label {
    margin-left: 0.5em !important;
}
</style>
  