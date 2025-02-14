<template>

	<html>
		<head>

		</head>

		<body>

			<div id="contenedor">

				<div class="bloque1">

					<p>Este es el Bloque 1 dentro del contenedor.</p>

				</div>

				<div class="bloque2">

					<p>Este es el contenido del Bloque 2 dentro del contenedor, este contiene mas texto, por eso debe ser mas largo.</p>

				</div>

			</div>

			<div class="bloque1">

				<p>Este es el Bloque 1 fuera del contenedor.</p>

			</div>

			<div class="bloque2">

				<p>Este es el Bloque 2 fuera del contenedor.</p>

			</div>

			<div class="v-container">
                <div v-for="(item, index) in myArray" :key="item.id" :style="{background: index % 2 == 0 ? '#e6e6e6' : '', color: index % 2 == 0 ? 'black' : '', display: index % 2 !== 0 ? 'none' : ''}">
                    {{item.name}} : {{item.roles.join(', ')}}
                </div>
			</div>
			<div class="btn" @click="generateOutput">
				Generar 
			</div>
			<div class="output">
				 {{output}}
			</div>

		</body>

	</html>

</template>

<script>

export default {

	name: 'SupportView',
	components: {

	},
	data () {
		return {
			myArray: [
				{ id: 1, name: 'Carlos', roles: [1, 2] },
				{ id: 2, name: 'Ana', roles: [2, 3] },
				{ id: 3, name: 'Luis', roles: [1, 3] },
				{ id: 4, name: 'Maria', roles: [2, 4] },
				{ id: 5, name: 'Pedro', roles: [3, 4] }
			],
			output:"",
			
		}
	},
	computed:{
		total() {
			return this.myArray.length
		}
	},
	methods:{
		generateOutput(){
			this.output = `El total de listado es: ${this.total}`
		}
	}

}

</script>

<style type="text/css">

  body {
		display: flex;
		justify-content: center;
		text-align: center;
        align-items: center;
	}

    p {
        padding: 10px;
    }
	
	#contenedor {
        display: flex;
        flex-wrap: wrap;
		width: 600px;
		margin: 0 auto;
		padding: 10px;
		margin-bottom: 10px;
		border: 1px dotted gray;
	}

    #contenedor > * {
        justify-content: flex-start;
        align-items: flex-start;
        margin: 10px
    }

    .bloque1, .bloque2 {
        width: 100px;
    }

    .bloque1 {
        margin-top: 70px;
        background-color: red;
        color: white
    }

    .bloque1 p {
        font-style: italic;
    }

    .bloque2 p {
        font-weight: bold;
    }

    .bloque2 {
        background-color: yellow;
        color: black;
    }
    .btn {
        background-color: white;
        color: black;
        padding: 5px;
        margin-left: 12px;
        border-radius: 4px;
    }
	.clear {
	
		clear:both;
	
	}	
</style>
