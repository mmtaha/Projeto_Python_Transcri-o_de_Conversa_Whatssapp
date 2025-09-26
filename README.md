# Projeto_Python_Transcrição_de_Conversa_Whatssapp

Este projeto é uma solução avançada de processamento de linguagem natural que automatiza a transcrição de conversas do WhatsApp, combinando a extração do histórico de mensagens textuais com a transcrição inteligente de áudios usando múltiplos motores de Speech-to-Text (STT).

Funcionalidades Principais
1. Processamento de Histórico de Conversas
Extrai e estrutura conversas de arquivos DOCX exportados do WhatsApp

Identifica e parseia metadados (data, hora, remetente, mensagem)

Organiza cronologicamente todo o histórico da conversa

2. Detecção Automática de Áudios
Reconhece automaticamente menções a arquivos de áudio (PTT-XXXXXX-WAXX.opus)

Cruzamento entre áudios mencionados e arquivos disponíveis

Filtragem inteligente para processamento apenas dos áudios relevantes

3. Sistema Multi-método de Transcrição
Implementa 10 métodos diferentes de STT em cascata:

Métodos Baseados em Whisper:

Transcrição direta em arquivos OPUS

Conversão via FFmpeg + Whisper

Processamento via Pydub + Whisper

Métodos Baseados em Google Speech:

Reconhecimento via Pydub (formato OPUS)

Conversão FFmpeg + Google Speech API

Processamento via Pydub (formato OGG)

Outros Motores:

Vosk (offline) via FFmpeg e Pydub

PocketSphinx (reconhecimento offline)

Google Cloud Speech API

4. Sistema Robusto de Fallback
Execução em cascata: se um método falha, automaticamente tenta o próximo

Tratamento de exceções para máxima estabilidade

Métricas de sucesso/fracasso por áudio processado

Tecnologias Utilizadas
Bibliotecas Principais:
whisper (OpenAI) - Transcrição de alta precisão

speech_recognition - Interface com múltiplas APIs de STT

pydub - Manipulação de áudio

vosk - Reconhecimento offline

python-docx - Processamento de documentos Word

pandas - Estruturação e exportação de dados

Ferramentas de Áudio:
FFmpeg - Conversão e processamento de formatos

SoX - Manipulação avançada de áudio

Fluxo de Processamento
Entrada: Documento DOCX exportado do WhatsApp + pasta com áudios OPUS

Extração: Parseamento do histórico textual e identificação de áudios

Conversão: Transformação de OPUS para WAV quando necessário

Transcrição: Aplicação sequencial dos 10 métodos de STT

Integração: Combinação de transcrições com histórico textual

Saída: CSV unificado com toda a conversa (texto + áudios transcritos)

Casos de Uso Ideais
Profissionais Autônomos:
Marceneiros, prestadores de serviço - Organizar orçamentos e combinados por áudio

Advogados - Documentar conversas importantes com clientes

Profissionais de saúde - Registrar orientações dadas por áudio

Negócios:
Atendimento ao cliente - Transcrição de solicitações por áudio

Reuniões comerciais - Documentação de tratativas por WhatsApp

Controle de pedidos - Organização de encomendas e especificações

Vantagens Competitivas
Robustez
10 métodos diferentes garantem alta taxa de sucesso

Sistema de fallback automático

Tolerante a falhas em APIs específicas

Precisão
Combinação de motores especializados

Suporte a diferentes qualidades de áudio

Otimizado para português brasileiro

Eficiência
Processamento automatizado de lotes

Integração direta com exportações do WhatsApp

CSV pronto para análise em planilhas

Resultados Esperados
Taxa de sucesso: 70-90% dependendo da qualidade dos áudios

Organização: Timeline completa da conversa em formato pesquisável

Produtividade: Redução de horas manuais de transcrição

Backup: Preservação digital de conversas importantes
