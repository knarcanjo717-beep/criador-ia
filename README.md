# Criador IA — primeira versão

Interface móvel para pedir um projeto Android, site ou outro programa. Um servidor Node chama a API da Groq, recebe arquivos de texto e entrega um ZIP do código-fonte. **Não gera APK, não compila e não testa os arquivos.** É um aplicativo web, ainda não um APK Android. O código gerado por IA pode conter erros, exigir dependências, ou não compilar. Revise antes de usar.

## Como executar

Requisitos: Node.js 18+, utilitário `zip` e uma chave de API da Groq com acesso e saldo. No terminal:

```sh
export GROQ_API_KEY='SUA_CHAVE'
export APP_TOKEN='UM_CODIGO_LONGO_E_SECRETO'
node server.js
```

Abra http://localhost:3000 e informe o APP_TOKEN em Configurações. A chave nunca deve ir para o aplicativo. O modelo padrão é `openai/gpt-oss-20b`; para alterar, defina `GROQ_MODEL`. A Groq oferece um plano gratuito sujeito a limites; planos pagos podem gerar custos.

## Próximos passos

- Criar um ambiente isolado para compilação de Android, instalar Android SDK/Gradle e gerar APK para download.
- Acrescentar testes, logs, tratamento de falhas, persistência e revisão dos arquivos.
- Empacotar a interface como app Android nativo e publicar o servidor com HTTPS.
- Antes de expor publicamente: autenticação robusta individual, limites de uso/custo e de requisições, proteção contra abuso, política de dados e isolamento forte. Este protótipo não está pronto para produção pública.
