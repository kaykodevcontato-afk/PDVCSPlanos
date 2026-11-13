# PDV Papelaria V1.2.0 — Dev Kayko

## GitHub Pages
Publique **somente** `index.html` e `servicos.html`. Mantenha o site via HTTPS. A página Dev Kayko abre `servicos.html` em outra aba.

## Planos — pagamento Pix manual
| Período | Valor |
|---|---:|
| 12 horas | R$ 9,90 |
| 1 dia (24 horas) | R$ 14,90 |
| 7 dias | R$ 39,90 |
| 15 dias | R$ 59,90 |
| 30 dias | R$ 89,90 |

1. O cliente escolhe o plano na tela de ativação e clica em **Solicitar Pix / enviar comprovante**. Isso abre WhatsApp com o valor e período selecionados.
2. Você envia seus dados Pix, confere o dinheiro **no aplicativo do banco**, e só então usa o gerador PRIVADO.
3. O gerador emite código assinado digitalmente, com horário inicial e final exatos (12h/24h/etc). Envie **apenas o código** para o cliente.
4. O cliente cola o código e ativa. Na renovação, gere novo código após novo pagamento.

### Chave Pix opcional na tela
Você pode definir `OWNER_PIX_KEY` dentro de `index.html` caso queira mostrar uma chave Pix pública para cópia. Sem chave configurada, o cliente pede os dados pelo WhatsApp. **Não existe QR Code Pix nem confirmação automática de pagamento nessa versão.** Nunca coloque senha ou token do banco no arquivo.

### Segurança e dados
- **Não publique** chave privada, `gerar_licenca.py`, histórico privado ou ZIP privado.
- Compatível com licenças antigas V1 (30 dias por datas). Novas licenças V2 usam duração exata a partir da emissão.
- Licenças são verificadas localmente por assinatura ECDSA P-256, mas a página pública e o relógio do computador podem ser alterados. **Não constitui bloqueio antifraude confiável**; para isso use backend.
- Código não está vinculado fortemente a aparelho ou pessoa; pode ser reutilizado em outro navegador. Não há revogação remota.
- Vendas, entradas, saídas e metas continuam salvas no navegador. A guia Backup faz exportação/restauração JSON, separadas da licença.
- Trocar de navegador ou limpar dados locais pode apagar registros; exporte backup regularmente.
