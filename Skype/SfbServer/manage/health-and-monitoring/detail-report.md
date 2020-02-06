---
title: Report Dettagli conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Riepilogo: informazioni sul report Dettagli conferenza usato in Skype for Business Server.'
ms.openlocfilehash: 73ca72bbfb7b003aaaa894a5bc9e417312d96caa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818006"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>Report Dettagli conferenza in Skype for Business Server

**Riepilogo:** Informazioni sul report Dettagli conferenza usato in Skype for Business Server.

Il report Dettagli conferenza offre informazioni dettagliate su tutti gli utenti che hanno partecipato a una conferenza. Ad esempio, puoi visualizzare informazioni come la data e l'ora in cui un utente ha partecipato alla conferenza, la data e l'ora in cui l'utente ha lasciato la conferenza e l'agente utente dell'endpoint usato per connettere l'utente alla conferenza. È anche possibile visualizzare le informazioni sul ruolo dell'utente in ogni conferenza, ad esempio relatore o partecipante. Forse la cosa più importante è vedere rapidamente gli utenti che partecipano e completano la conferenza e che gli utenti non sono stati in grado di partecipare e completare la conferenza con successo.

## <a name="accessing-the-conference-detail-report"></a>Accesso al report Dettagli conferenza

È possibile accedere al report Dettagli conferenza dai report seguenti:

- [Report di controllo ammissione chiamata](call-admission-control-report.md) (facendo clic sulla metrica di dettaglio per una conferenza)

- [Report elenco errori](failure-list-report.md) (facendo clic sulla metrica conferenza)

- [Report attività utente](call-diagnostic-reports-per-user.md) (facendo clic sulla metrica URI conferenza)

Dal report Dettagli conferenza è possibile accedere al [report di diagnostica](diagnostic-report.md) facendo clic sulla metrica rapporto di diagnostica (dettaglio).

## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report Dettagli conferenza.

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nella sezione informazioni conferenza del report Dettagli conferenza.

**Metriche delle informazioni sulla conferenza**


| **Nome**                 | **Descrizione**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **URI conferenza** <br/> | URI assegnato alla conferenza. Ad esempio:  <br/> SIP: kmyer@litwareinc. com; GRUU; opaque = app: conf: stato attiva: ID: drg2y8v4  <br/> |
| **FQDN del pool** <br/>      | Nome di dominio completo del pool di registrazione o del server perimetrale coinvolto in una sessione.  <br/>                             |
| **Ora di inizio** <br/>     | Data e ora in cui è stata avviata la conferenza.  <br/>                                                                          |
| **Organizzatore** <br/>      | Indirizzo SIP dell'utente che ha organizzato la conferenza.  <br/>                                                               |
| **Ora di fine** <br/>       | Data e ora di fine della conferenza.  <br/>                                                                            |

Nella tabella seguente sono elencate le informazioni fornite nella sezione partecipazione alla conferenza del report Dettagli conferenza.

**Metriche per la partecipazione alla conferenza**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Utente** <br/> |Indirizzo SIP dell'utente che ha partecipato alla conferenza.  <br/> |
|**Ruolo** <br/> |Ruolo (ad esempio, relatore) riprodotto dal partecipante alla conferenza.  <br/> |
|**Connettività** <br/> |Connettività di rete (in genere da interno o da esterno) per il partecipante.  <br/> |
|**Tempo di partecipazione** <br/> |Data e ora in cui il partecipante ha partecipato alla conferenza.  <br/> |
|**Ora di uscita** <br/> |Data e ora in cui il partecipante ha lasciato la conferenza.  <br/> |
|**Agente utente** <br/> |Identificatore per il software usato dall'endpoint del partecipante.  <br/> |
|**Report di diagnostica** <br/> |Fornisce informazioni di diagnostica e risoluzione dei problemi. Inclusi i codici di risposta SIP, le intestazioni di diagnostica, le ore di conferenza e gli ID di diagnostica per le sessioni non riuscite.  <br/> |

Nella tabella seguente sono elencate le informazioni fornite nella sezione modalità conferenza del report Dettagli conferenza.

**Metriche delle modalità conferenza**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Utente** <br/> |Indirizzo SIP dell'utente che ha partecipato alla conferenza.  <br/> |
|**Tempo di partecipazione** <br/> |Data e ora in cui il partecipante ha partecipato alla conferenza.  <br/> |
|**Ora di uscita** <br/> |Data e ora in cui un partecipante ha lasciato la conferenza.  <br/> |
|**URI di conferenza server** <br/> |URI per il server delle conferenze usato nella conferenza.  <br/> |
|**Report di diagnostica** <br/> |Fornisce informazioni di diagnostica e risoluzione dei problemi. Inclusi i codici di risposta SIP, le intestazioni di diagnostica, le ore di conferenza e gli ID di diagnostica per le sessioni non riuscite.  <br/> |


