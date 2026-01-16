Template para monitorar FortiAPs gerenciados por FortiGate (Wireless Controller) via SNMP, usando LLD (Discovery) e triggers para UP/DOWN.

## Compatibilidade
- Zabbix: 6.4.x
- FortiGate: Wireless Controller habilitado (FortiAPs managed)

## O que monitora
- Descoberta automática de FortiAPs (LLD) usando o nome do AP
- Status por AP via SNMP:
  - 1 = DOWN
  - 2 = UP
- Trigger por AP quando status = 1

## OIDs usados
- Discovery (AP name):
  - 1.3.6.1.4.1.12356.101.14.4.4.1.2.1
- Status (UP/DOWN):
  - 1.3.6.1.4.1.12356.101.14.4.4.1.7.1.{#SNMPINDEX}

## Como instalar
1. No Zabbix, crie (se não existir) o grupo: `Templates/Network`
2. Importe o XML:
   - `zbx_export_template_fortigate_fortiap_snmp_6.4.xml`
3. Vincule o template ao host do FortiGate
4. Execute a descoberta (LLD) manualmente na primeira vez:
   - Host -> Discovery rules -> Run now

## Mapa visual
Recomenda-se criar Map com elementos do tipo Trigger para cada AP:
- Verde (OK) quando UP
- Vermelho (PROBLEM) quando DOWN

## Licença
MIT
EOF
