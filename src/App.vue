<template>
  <div class="container">
    <div class="container info-group">
    <div class="row">
      <img src="./assets/face3.png" />
      <h5 class="card-title">3º FACE A FACE MULHERES/MOÇAS DA IGREJA BETHEL VILA VELHA/ES</h5>
          <p class="card-text">FORMULÁRIO DE INSCRIÇÃO PARA PARTICIPANTE</p>
    </div>
    </div>

    <form class="">
      <h5>Informações Pessoais</h5>
      <div class="container info-group">
        <div class="row">
          <div class="col-md-7 mb-2">
            <label for="nomeCompleto" class="form-label">Nome Completo:<strong class="required">*</strong></label>
            <input type="text" class="form-control" id="nomeCompleto">
            <span>Este campo é obrigatório</span>
          </div>
          <div class="col-md-2 mb-2">
            <label for="idade" class="form-label">Idade:<strong class="required">*</strong></label>
            <input type="number" min="10" max="100" class="form-control" id="idade">
          </div>
          <div class="col-md-3 mb-2">
            <label for="camisa" class="form-label">Tamanho da Camisa:<strong class="required">*</strong></label>
            <select id="camisa" class="form-select">
              <option selected>Escolha uma opção</option>
              <option>PP</option>
              <option>P</option>
              <option>M</option>
              <option>G</option>
              <option>GG</option>
              <option>XG</option>
              <option>G1</option>
              <option>G2</option>
              <option>G3</option>
            </select>
          </div>
        </div>
        <div class="row">
          <div class="col-md-2">
            <label class="form-label">Casada:<strong class="required">*</strong></label><br>
            <div class="form-check form-check-inline">
              <input v-model="casada" class="form-check-input" name="casada" type="radio" id="inlineCheckbox1" value="1">
              <label class="form-check-label" for="">Sim</label>
            </div>
            <div class="form-check form-check-inline">
              <input v-model="casada" class="form-check-input" name="casada" type="radio" id="inlineCheckbox2" value="0">
              <label class="form-check-label" for="inlineCheckbox2">Não</label>
            </div>
          </div>
          <div class="col-md-5">
            <label class="form-label">Gestante:<strong class="required">*</strong></label><br>
            <div class="form-check form-check-inline">
              <input class="form-check-input" name="gestante" type="radio" id="inlineCheckbox1" value="1">
              <label class="form-check-label" for="">Sim</label>
            </div>
            <div class="form-check form-check-inline">
              <input class="form-check-input" name="gestante" type="radio" id="inlineCheckbox1" value="2">
              <label class="form-check-label" for="">Sim, necessito de cuidados especiais</label>
            </div>
            <div class="form-check form-check-inline">
              <input class="form-check-input" name="gestante" type="radio" id="inlineCheckbox2" value="0">
              <label class="form-check-label" for="">Não</label>
            </div>
          </div>
          <div class="col-md-5">
            <label for="meses" class="form-label">Meses de gestação:<strong class="required">*</strong></label>
            <input type="number" min="0" max="9" class="form-control" id="meses">
          </div>
        </div>
      </div>
      <hr />
      <h5>Informações de Contato</h5>
      <div class="container info-group">
        <div class="row">
          <div class="col-md-8">
            <label for="cuidados" class="form-label">Endereço Completo:<strong class="required">*</strong></label>
            <input type="text" class="form-control" id="cuidados" placeholder="">
          </div>
          <div class="col-md-4">
            <label for="tel" class="form-label">Telefone de Contato com DDD:<strong class="required">*</strong></label>
            <input type="text" class="form-control" id="tel">
          </div>
        </div>
        <div v-show="casada == '1'" class="row">
          <div class="col-md-8">
            <label for="esposo" class="form-label">Nome do Esposo:<strong class="required">*</strong></label>
            <input type="text" class="form-control" id="esposo" placeholder="Sr Fulano de Tal">
          </div>
          <div class="col-md-4">
            <label for="telEsposo" class="form-label">Telefone de Esposo com DDD:<strong class="required">*</strong></label>
            <input type="text" class="form-control" id="telEsposo">
          </div>
        </div>
        <div class="row">
          <div class="col-md-8">
            <label for="pais" class="form-label">Nome dos Pais:<strong class="required">*</strong></label>
            <input type="text" class="form-control" id="pais" placeholder="">
          </div>
          <div class="col-md-4">
            <label for="pais" class="form-label">Telefone dos Pais com DDD:<strong class="required">*</strong></label>
            <input type="text" class="form-control" id="pais" placeholder="">
          </div>
        </div>
      </div>
      <hr />
      <h5>Informações de Saúde</h5>
      <div class="container info-group">
        <div class="row">
          <div class="col-md-6">
            <label  class="form-label">Toma algum medicamento:<strong class="required">*</strong></label><br>
            <div class="form-check form-check-inline">
              <input v-model="tomaMedicamento" class="form-check-input" type="radio" value="1">
              <label class="form-check-label" for="medicamentoSim">Sim</label>
            </div>
            <div class="form-check form-check-inline">
              <input v-model="tomaMedicamento" class="form-check-input" type="radio" value="0">
              <label class="form-check-label" for="medicamentoNao">Não</label>
            </div>
          </div>
          <div v-show="tomaMedicamento == '1'" class="col-md-6">
            <label for="telEsposo" class="form-label">Informe qual medicamento:</label>
            <input type="text" class="form-control" id="telEsposo">
          </div>
        </div>
        <div class="row" >
          <div class="col-md-6">
            <label for="medicamento" class="form-label">Tem alguma alergia a medicamento:<strong class="required">*</strong></label><br>
            <div class="form-check form-check-inline">
              <input v-model="alergiaMedicamento" class="form-check-input" type="radio"  value="1">
              <label class="form-check-label">Sim</label>
            </div>
            <div class="form-check form-check-inline">
              <input v-model="alergiaMedicamento" class="form-check-input" type="radio"  value="0">
              <label class="form-check-label">Não</label>
            </div>
          </div>
          <div  v-show="alergiaMedicamento == '1'" class="col-md-6">
            <label for="telEsposo" class="form-label">Informe qual medicamento:<strong class="required">*</strong></label>
            <input type="text" class="form-control">
          </div>
        </div>
        <div class="row">
          <div class="col-md-6">
            <label for="medicamento" class="form-label">Tem alguma restrição ou alergia alimentar:<strong class="required">*</strong></label><br>
            <div class="form-check form-check-inline">
              <input v-model="restricaoAlimentar"  class="form-check-input" type="radio" id="medicamentoSim" value="1">
              <label class="form-check-label" for="medicamentoSim">Sim</label>
            </div>
            <div class="form-check form-check-inline">
              <input v-model="restricaoAlimentar"  class="form-check-input" type="radio" id="medicamentoNao" value="0">
              <label class="form-check-label" for="medicamentoNao">Não</label>
            </div>
          </div>
          <div v-show="restricaoAlimentar == '1'" class="col-md-6">
            <label for="telEsposo" class="form-label">Qual(is) alimento(s):<strong class="required">*</strong></label>
            <input type="text" class="form-control" id="telEsposo">
          </div>
        </div>
      </div>
      <hr />
      <h5>Informações da Igreja</h5>
      <div class="container info-group">
        <div class="row mb-3">
          <div class="col-md-6">
            <label for="inputState" class="form-label">Membro de qual Igreja:<strong class="required">*</strong></label>
            <select v-model="infoIgreja" id="inputState" class="form-select">
              <option selected>Escolha uma opção</option>
              <option value="1">BETHEL VILA VELHA</option>
              <option value="2">BETHEL GURIRI</option>
              <option value="3">OUTRA IGREJA</option>
              <option value="4">FUI CONVIDADA POR UM AMIGO (A)</option>
            </select>
          </div>
          <div v-show="infoIgreja =='3'" class="col-md-6">
            <label for="telEsposo" class="form-label">Informe o nome da Igreja:<strong class="required">*</strong></label>
            <input type="text" class="form-control" id="telEsposo">
          </div>
          <div v-show="infoIgreja =='4'" class="col-md-6">
            <label for="telEsposo" class="form-label">Informe o nome e o telefone de quem te convidou:<strong class="required">*</strong></label>
            <input type="text" class="form-control" id="telEsposo">
          </div>
        </div>
        <div class="row">
          <div class="col-md-6">
            <label for="inputState" class="form-label">Célula:<strong class="required">*</strong></label>
            <select id="inputState" class="form-select">
              <option selected>Escolha uma opção</option>
              <option>BETHEL VILA VELHA</option>
              <option>BETHEL GURIRI</option>
              <option>OUTRA IGREJA</option>
              <option>FUI CONVIDADA POR UM AMIGO (A)</option>
            </select>
          </div>
          <div class="col-md-6">
            <label for="telEsposo" class="form-label">Informe o nome do seu líder de célula ou pastor(a):</label>
            <input type="text" class="form-control" id="telEsposo">
          </div>
        </div>
      </div>
      <hr />
      <h5>Outras Informações</h5>
      <div class="container info-group">
        <div class="row">
          <div class="col-md-6">
            <label for="floatingTextarea" class="form-label">Descreva seus sonhos pessoais e ministeriais (o que você
              deseja
              alcançar e qual área você deseja servir no reino de deus):<strong class="required">*</strong></label>
            <textarea class="form-control" placeholder="Deixe o seu comentário aqui..." id="floatingTextarea"></textarea>
          </div>

        </div>
        <div class="row">
          <div class="col-md-6">
            <label for="observation" class="form-label">Deixa aqui uma observação que seja importante pra você:</label>
            <textarea class="form-control" placeholder="Deixe o seu comentário aqui..." id="observation"></textarea>
          </div>
        </div>
      </div>

      <hr />
      <div class="container info-group">
        <div class="row">
          <div class="col-12">
            <div class="form-check">
              <input class="form-check-input" type="checkbox" id="gridCheck">
              <label class="form-check-label advice" for="gridCheck">
                Estou ciente que em caso de desistência, o valor da inscrição só será devolvido até 20 (vinte) dias antes do encontro.
              </label>
            </div>
          </div>
        </div>
      </div>
<div class="container info-group">
  <div class="row">
      <div class="col-12">
        <div class="form-check">
          <input class="form-check-input" type="checkbox" id="gridCheck">
          <p class="advice">Declaro que autorizo o uso da minha imagem pessoal, a título gratuito, pela equipe do Ministério Face a Face
            com Deus, o qual está subordinado à Igreja Bethel Vila Velha, nas filmagens e divulgações, dentre as quais, o
            vídeo retrospectivo da edição do evento realizado entre os dias 17/03/2023 a 19/03/2023, além dos demais
            materiais, os quais serão publicados nas redes sociais e demais mídias da Igreja Bethel Vila Velha com
            abrangência em todo território nacional. Sem que nada haja a ser reclamado a título de direitos conexos à
            minha imagem ou a qualquer outro e por fim, firmo este termo segundo legislação vigente.</p>
        </div>
      </div>
  </div>
</div>

      <hr />
      <div class="col-12">
        <button type="submit" class="btn btn-primary">Enviar</button>
      </div>
    </form>
  </div>
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      casada: "",
      tomaMedicamento: "",
      alergiaMedicamento: "",
      restricaoAlimentar: "",
      infoIgreja: ""
    }
  },
  methods: {
    isCasada(e) {
      console.log(e);
    }
  }
}
</script>
<style>
body {
  background-color: rgb(241 245 249);
}

.info-group {
  margin-bottom: 20px;
  border-radius: 10px;
  padding-bottom: 20px;
  background-color: #fff;
  padding-top: 10px;
  box-shadow: rgb(17 17 26 / 10%) 0px 0px 6px;
}
.required {
  margin-left: 3px;
  color: #ED6A5E;
}
.advice {
  text-align: justify;
  font-size: 0.875em;
}
</style>
