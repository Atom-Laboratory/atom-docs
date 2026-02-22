# Proposta de Orçamento de Componentes

## Projeto: Braço Robótico InMoov

---

### Tabela de Componentes

| Código  | Componente                                                        | Qtd. |
|---------|-------------------------------------------------------------------|------|
| EL001   | Servo Motor MG996r                                 | 2    |
| EL007   | Módulo PWM PCA9685 I2C - 16 Canais para Servo                     | 1    |
| EL009   | Módulo Sensor de Corrente e Tensão INA219                                     | 1    |
| EL014   | Conversor de Nível Lógico 3,3-5V Bidirecional 8 Canais            | 1    |
| EL013   | Acelerômetro e Giroscópio 3 Eixos 6 DOF MPU-6050 - GY-521         | 1    | 
| EL015   | Pack NiMH 6V 2500 mAh                                              | 1    |

---

### Justificativa dos Componentes

- **[PCA9685 PWM:](https://www.eletrogate.com/modulo-pwm-pca9685-i2c-16-canais-para-servo?utm_source=Site&utm_medium=GoogleMerchant&utm_campaign=GoogleMerchant&gad_source=1&gad_campaignid=22470016551&gclid=Cj0KCQjwrJTGBhCbARIsANFBfgvZgBmQ6ljjLIDDGlWy1KMZL0GS5mE0x2x1ze2TGPCTE-PFUNopJYsaAoQhEALw_wcB)** Essencial para gerar sinais PWM estáveis para os diversos servos do braço InMoov.
- **[Módulo Sensor de Corrente e Tensão INA219:](https://www.eletrogate.com/sensor-de-corrente-dc-ina219-i2c?utm_source=Site&utm_medium=GoogleMerchant&utm_campaign=GoogleMerchant&gad_source=1&gad_campaignid=22470016551&gbraid=0AAAAADqxjs8l-pfZk4iJo0TMZkY3VXJza&gclid=Cj0KCQjwrJTGBhCbARIsANFBfguY1c57FjRn4d6IbtuoWq4kGgviCp0iREGJD06X1U19ORAwWaGP1OsaAs62EALw_wcB)** Útil para monitorar o consumo dos servos, detectar picos e evitar falhas.
- **[Conversores de Nível Lógico:](https://www.eletrogate.com/conversor-de-nivel-logico-33-5v-bidirecional-8-canais?utm_source=Site&utm_medium=GoogleMerchant&utm_campaign=GoogleMerchant&gad_source=1&gad_campaignid=22470016551&gbraid=0AAAAADqxjs8l-pfZk4iJo0TMZkY3VXJza&gclid=Cj0KCQjwrJTGBhCbARIsANFBfgsSHdI-WUVrc9d-LyDuKD1g-yyNaU2m6scG2nyA3c2p1kGFZChMUsIaAid-EALw_wcB)** Imprescindíveis para interface segura entre dispositivos de 3.3V e 5V.
- **[MPU-6050 (Acelerômetro/Giroscópio):](https://www.eletrogate.com/acelerometro-e-giroscopio-3-eixos-6-dof-mpu-6050-gy-521?utm_source=Site&utm_medium=GoogleMerchant&utm_campaign=GoogleMerchant&gad_source=1&gad_campaignid=22470016551&gclid=Cj0KCQjwrJTGBhCbARIsANFBfgswCtRoGtz3MJUM4U0l55GYhUm1dwFukuGPPNdx__6k4QBRdx7NSHIaAqOBEALw_wcB)** Fornece feedback de posição/orientação, útil para controle refinado do antebraço.
- **[Pack NiMH 6V 2500 mAh:](https://www.mercadolivre.com.br/bateria-6v-2700mah-aa-nimh-com-fio-terminal-recarregavel/up/MLBU1708410431?pdp_filters=item_id:MLB1166770746#is_advertising=true&searchVariation=MLBU1708410431&backend_model=search-backend&position=1&search_layout=grid&type=pad&tracking_id=9abec7b1-cf7c-4f16-85e4-116f94832060&ad_domain=VQCATCORE_LST&ad_position=1&ad_click_id=Y2E3ZDE4NGUtYmY1ZC00ODRlLTk1MGQtNGViNTk1MzA0MmU3)** Fonte de energia portátil para alimentar o sistema, garantindo mobilidade e autonomia durante operações.


---

**Obs:** 
