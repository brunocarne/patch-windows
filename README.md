# Playbook de Atualização Windows

Este playbook Ansible automatiza o processo de instalação de atualizações do Windows em múltiplos servidores, incluindo verificações de pré-requisitos e reinicializações automáticas quando necessário.

## Funcionalidades

- ✅ Execução em lotes de 15 servidores simultaneamente
- 🔍 Verificação de espaço em disco
- 🔒 Gerenciamento automático de políticas de execução PowerShell
- 🔄 Reinicialização automática quando necessário
- 📊 Relatório de atualizações instaladas
- 🎯 Foco em atualizações de segurança e críticas

## Pré-requisitos

- Ansible 2.9+
- Módulo `serverscom.mitogen`
- Acesso WinRM configurado nos hosts Windows
- Mínimo de 7GB de espaço livre em disco nos hosts

## Estrutura do Projeto

```
.
├── check_update_windows.yml
├── roles/
│   └── vars/
│       └── vars.yml
└── README.md
```

## Configuração

1. Ajuste as variáveis em `roles/vars/vars.yml`
2. Configure seu inventário Ansible com os hosts Windows
3. Certifique-se que o WinRM está configurado nos hosts

## Execução

```bash
ansible-playbook check_update_windows.yml -i seu_inventario
```

### Tags Disponíveis

- `pre_check`: Executa apenas verificações preliminares
- `check_resources`: Verifica recursos do sistema
- `update`: Executa apenas a instalação de atualizações
- `post_update`: Executa apenas tarefas pós-atualização
- `cleanup`: Executa apenas tarefas de limpeza

## Comportamento do Playbook

1. Verifica pré-requisitos do sistema
2. Valida espaço em disco disponível
3. Instala atualizações críticas e de segurança
4. Reinicia o servidor se necessário
5. Gera relatório de execução

## Contribuição

Sinta-se à vontade para contribuir com melhorias através de Pull Requests.

