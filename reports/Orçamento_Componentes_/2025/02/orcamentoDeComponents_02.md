# Proposta de Orçamento de Componentes

## Projeto: Braço Robótico InMoov

---

### Tabela de Componentes

| Código  | Componente                                                        | Qtd. | Preço (R$)         |
|---------|-------------------------------------------------------------------|------|--------------------|
| EL004   | ESP32                                                             | 0    | 56,00              |
| EL006   | Fonte 6V 1A Bivolt                                                | 1    | 17,00              |
| EL007   | Módulo PWM PCA9685 I2C - 16 Canais para Servo                     | 1    | 40,00              |
| EL008   | Módulo Conversor USB 2.0 para TTL CH340G - 6 PINOS                | 1    | 15,00              |
| EL009   | Módulo Sensor de Corrente 20A                                     | 1    | 15,00              |
| EL010   | Conversor de Nível Lógico 3.3V-5V Bidirecional - 4 Canais         | 4    | 28,00 (7,00 cada)  |
| EL014   | Conversor de Nível Lógico 3,3-5V Bidirecional 8 Canais            | 1    | 29,95 (17,95 + 12) |
| EL011   | Raspberry Pi Zero 2 W                                             | 1    | 200,00             |
| EL012   | Placa de Extensão T GPIO para Raspberry Pi + Cabo 40 Pinos - Azul | 1    | 25,00              |
| EL013   | Acelerômetro e Giroscópio 3 Eixos 6 DOF MPU-6050 - GY-521         | 1    | 30,00              |
| **Total estimado** | | | **400,95** |


---

### Justificativa dos Componentes

- **ESP32:** Controlador extra para distribuir o controle entre braços e mãos, proporcionando modularidade ao sistema.
- **Fonte 6V 1A:** Fonte básica, porém insuficiente para múltiplos servos MG996R; será necessário atualizar para maior capacidade.
- **PCA9685 PWM:** Essencial para gerar sinais PWM estáveis para os diversos servos do braço InMoov.
- **Módulo USB-TTL (CH340G):** Permite programação e comunicação com microcontroladores como ESP32/Arduino.
- **Sensor de Corrente:** Útil para monitorar o consumo dos servos, detectar picos e evitar falhas.
- **Conversores de Nível Lógico:** Imprescindíveis para interface segura entre dispositivos de 3.3V e 5V.
- **Raspberry Pi Zero 2 W:** Central de visão computacional leve ou servidor para integração dos módulos.
- **Placa de Expansão T-GPIO:** Facilita o acesso a múltiplos pinos GPIO do Pi Zero 2 W.

- **[MPU-6050 (Acelerômetro/Giroscópio):](https://www.eletrogate.com/acelerometro-e-giroscopio-3-eixos-6-dof-mpu-6050-gy-521?utm_source=Site&utm_medium=GoogleMerchant&utm_campaign=GoogleMerchant&gad_source=1&gad_campaignid=22470016551&gclid=Cj0KCQjwrJTGBhCbARIsANFBfgswCtRoGtz3MJUM4U0l55GYhUm1dwFukuGPPNdx__6k4QBRdx7NSHIaAqOBEALw_wcB)** Fornece feedback de posição/orientação, útil para controle refinado do antebraço.


---

**Observação:** Todos os itens listados encontram-se fora de estoque no momento. Recomenda-se verificar disponibilidade e possíveis alternativas antes da aquisição.
