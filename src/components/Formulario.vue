<script setup>
const props = defineProps([ 'selecionarOperacao', 'valorX', 'valorY', 'executarOperacao', 'resultado' ])
</script>

<template>
    <div class = "container card ">
        <form >
            
                <div class = "row card mb-4">
                    <div class = "col badge bg-secondary">
                        <h2>Calculadora</h2>
                    </div>
                </div>
                <div class="row">
                    <div class="col-md-4 mb-2">
                        <input @change = "props.valorX"   required class="form-control" type="number" placeholder="Valor x">
                    </div>
                    <div class="col-md-4">
                        <input @change = "props.valorY"   required class="form-control mb-2" type="number" placeholder="Valor y">
                    </div>

                    <div class="col-md-4 mb-2">
                        <select @click = "props.executarOperacao"  @change = "props.selecionarOperacao" class="form-control" name="" id="">
                            <option value="">Selecione a operação</option>
                            <option value="+">Somar</option>
                            <option value="-">Subtrair</option>
                            <option value="*">Multiplicar</option>
                            <option value="/">Dividir</option>
                        </select>
                    </div>
                    
                </div>
                <div class = "row">
                    <div class="col-mb-3  ">
                        <h4 class = "card p-2" v-if = " resultado || resultado === 0" >Resultado: {{ props.resultado }} </h4>
                        <h4 class = "card p-2" v-else >O valor de x e y não podem está vazios </h4>
                    </div>
                </div>
        
        </form>
    </div>
</template>

