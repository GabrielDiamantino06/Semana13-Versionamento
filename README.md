algoritmo "MensageiroDoPipelineLocal"

// --- Nosso canal de alertas ---
procedimento enviarAlerta(status: caractere, texto: caractere)
inicio
   escreval("")

   se (status = "sucesso") entao
      escreval("✅ --- ALERTA DE SUCESSO ---")
      escreval("Mensagem: ", texto)
      escreval("---------------------------")
   senao
      escreval("❌ --- ALERTA DE ERRO ---")
      escreval("Mensagem: ", texto)
      escreval("-------------------------")
   fimse

   escreval("")
fimprocedimento


// --- Função que simula o build ---
funcao executarBuild(): logico
inicio

   // Mude para verdadeiro ou falso para testar
   retorne verdadeiro

fimfuncao


// --- Programa principal ---
var
   buildSucesso: logico

inicio

   buildSucesso <- executarBuild()

   se (buildSucesso) entao
      enviarAlerta("sucesso","O build da versão 1.2.0 foi concluído.")
   senao
      enviarAlerta("erro","O build falhou no commit a3b1c9.")
   fimse

fimalgoritmo
