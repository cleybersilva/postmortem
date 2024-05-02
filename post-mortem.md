# Post-mortem

# Resumo

A implantação do nosso serviço de autenticação deixou alguns clientes impossibilitados de fazer login no nosso aplicativo por um período de 9 minutos. O problema foi relatado pelo Suporte ao Cliente cinco minutos antes de nosso sistema de alerta detectar o problema. Revertemos a implantação incorreta que restaurou o serviço imediatamente. Aproximadamente 50 usuários foram afetados pelo problema e entramos em contato com eles diretamente para pedir desculpas.

---

### 🔗 Links Importantes

- 💬 [Slack channel](https://slack.com/app_redirect?team=T02PL2PMTE2&channel=C04SXFWCKDE)
- 🌐 [Incident homepage](https://app.incident.io/incidents/197?ctx=ZuwDQHG%2BgcUDYFHmEMoGmCOtqIob2nwoZusogPu%2B4xoGTbIf%2Bm1c7gXPWr2Jo19rX0YptWC1P9rUj0wD%2Bussv9j2cJfGwhrA3BJJ8ipm0laFJFxjtxLEa2IhHa76%2Fi5k3wBPekYayLfsqww%3D)

---

### ℹ️ Key Information

- **Incident Type:** Platform
- **Severity:** Minor

---

### 👪 Team

- **Incident Lead:** Katie Hewitt
- **Reporter:** Lucy Jennings
- **Active participants:** Katie Hewitt, Lawrence Jones, Martha Lambert

### ⏱️ Key Timestamps

- **Reported:** March 3, 2023 9:36 AM (UTC)
- **Impact start:** March 3, 2023 9:36 AM (UTC)
- **Fixed:** March 3, 2023 9:45 AM (UTC)
- **Closed:** March 3, 2023 10:12 AM (UTC)

---

### ⏳ Durations

- **Incident duration:** 36 minutes
- **Time to resolve:** 9 minutes

---

# Incident Timeline

<aside>
📆 All timestamps in UTC

</aside>

| Date / Time  | Event |
| --- | --- |
| 2023-03-03 |  |
| 09:36:09 | The incident was automatically opened from an alert triggered by our monitoring system, Prometheus. |
| … | … |
| … | … |
| … | … |
| 10:12:10 | We confirmed no additional errors or alerts were firing and closed the incident |

---

# Contributors

<aside>
➕ *What were the contributing factors for this incident? Think of these less as causes, and more as the set of conditions that had to manifest for this incident to occur, or reach the assigned severity.*

</aside>

| Summary | Details |
| --- | --- |
| The on-call engineer was on the subway at the time | We have a 15 minute response SLA for on-call engineers, and the engineer who was first responder for this incident was delayed on a subway train. This increased the time it took for us to act on resolving this incident. |
| … | … |

# Mitigators

<aside>
➖ *What things prevented this incident from being worse? Think of these as the set of things that reduced the overall impact.*

</aside>

| Summary | Details |
| --- | --- |
| Deployment transparency | We recently rolled out some changes to connect our service deployments to the #deployments-pulse channel in Slack. We noticed early into the incident that the timestamps of errors correlated with the deployment of the authentication service, which helped us to make the decision to roll back more quickly. |
| … | … |

# Learnings and Risks

<aside>
🎓 *What did we learn here, and what risks has this uncovered?*

</aside>

| Summary | Details |
| --- | --- |
| Our process for requesting on-call overrides is too cumbersome | The on-call engineer knew they’d be out of signal for >15 minutes, but the process for requesting an override was sufficiently cumbersome that they decided to take the risk rather than handing over to someone else. |
| … | … |

# Follow-up actions

<aside>
ℹ️ *These are logged here for convenience during the debrief meeting, and migrated into our issue tracker via [incident.io](http://incident.io) afterwards.*

</aside>

| Action | Assignee |
| --- | --- |
| Investigate options for reducing the effort required to request an on-call override. | Martha Lambert |
| … | … |