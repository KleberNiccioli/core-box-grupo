# Laboratório SSO — tokens de exemplo (Dia 03)

Analise estes tokens no inspetor do Core Box (`/sso/inspecionar`) e teste a reação
do `/sso/callback`. Use o roteiro de análise do Capítulo 4 do Caderno do Aluno.

- token_01_maria_hs256.jwt  — token "normal" do IdP de homologação
- token_02_alg_none.jwt     — token sem assinatura
- token_03_admin_forjado.jwt — token com privilégios elevados
- token_04_expirado.jwt     — token fora da validade

(O script gerar_tokens.py recria estes arquivos; uso do professor.)
