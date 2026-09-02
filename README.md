# Chamado Rápido — Engenharia Clínica

Aplicativo Cordova para abertura de chamados em menos de um minuto. O usuário lê o QR Code do equipamento, confirma a falha, responde à triagem de segurança e abre o WhatsApp com a mensagem pronta.

## Recursos

- Leitura de QR Code pela câmera;
- Busca por patrimônio, série ou código;
- Dados do equipamento preenchidos automaticamente;
- Triagem de possível evento adverso, incidente sem dano, quase falha, condição de risco ou queixa técnica;
- Orientação para registro no SIGQuali quando aplicável;
- Mensagem pronta para o WhatsApp `(84) 99447-2995`;
- Nenhuma coleta de nome, prontuário ou dado clínico do paciente;
- Base local que funciona offline.

## Estrutura

- `www/index.html` — aplicativo completo;
- `www/equipamentos.json` — base local de equipamentos;
- `resources/icon.png` — ícone e splash do aplicativo;
- `config.xml` — configuração Cordova/Android;
- `package.json` — plugins e dependências;
- `.github/workflows/gerar-apk.yml` — geração automática do APK;
- `saida/` — pasta onde o GitHub salvará o APK.

## Atualizar os equipamentos

Edite `www/equipamentos.json`. Cada equipamento deve seguir este modelo:

```json
{
  "id": "008528",
  "patrimonio": "008528",
  "nome": "Cardioversor",
  "marca": "Instramed",
  "modelo": "CardiMax",
  "serie": "092020 CM16039",
  "setor": "Urgência",
  "criticidade": "Alta"
}
```

O QR Code pode conter somente o patrimônio, uma URL com `?patrimonio=008528` ou um objeto JSON com os dados do equipamento.

## Gerar o APK pelo GitHub

1. Crie um repositório vazio no GitHub.
2. Envie o conteúdo desta pasta para a raiz do repositório.
3. Abra a aba **Actions**.
4. Selecione **Gerar APK — Chamado Rápido EC**.
5. Toque em **Run workflow**.
6. O APK será disponibilizado como artefato e salvo em `saida/Chamado_Rapido_EC.apk`.

## Observação de segurança

A triagem é um apoio inicial. A classificação final e a decisão sobre SIGQuali ou comunicação externa devem ser realizadas pela Engenharia Clínica em conjunto com o NSP/Gerência de Risco.
