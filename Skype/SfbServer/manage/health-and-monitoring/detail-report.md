---
title: Rapporto Dettagli conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Riepilogo: informazioni sul rapporto Dettagli conferenza utilizzato in Skype for Business Server.'
ms.openlocfilehash: 245691fcb304a872942be4d5a9aabe8183b4db14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816906"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>Rapporto Dettagli conferenza in Skype for Business Server

**Riepilogo:** Informazioni sul rapporto Dettagli conferenza utilizzato in Skype for Business Server.

Il Rapporto Dettagli conferenza offre informazioni dettagliate su tutti gli utenti che hanno partecipato a una conferenza. È ad esempio possibile conoscere la data e l'ora in cui un utente si è unito alla conferenza o in cui l'ha abbandonata e l'agente utente dell'endpoint utilizzato per connettere tale utente alla conferenza. È anche possibile visualizzare informazioni sul ruolo dell'utente in ciascuna conferenza (relatore o partecipante). E ancora più importante, è possibile sapere rapidamente quali utenti si sono uniti alla conferenza e l'hanno completata e quali non ci sono riusciti.

## <a name="accessing-the-conference-detail-report"></a>Accesso al Rapporto Dettagli conferenza

Il Rapporto Dettagli conferenza è accessibile dai rapporti seguenti:

- [Call Admission Control Report](call-admission-control-report.md) (facendo clic sulla metrica Dettaglio per una conferenza)

- [Failure List Report](failure-list-report.md) (facendo clic sulla metrica Conferenza)

- [User Activity Report](call-diagnostic-reports-per-user.md) (facendo clic sulla metrica URI conferenza)

Dal Rapporto Dettagli conferenza è possibile accedere al [Diagnostic Report](diagnostic-report.md) facendo clic sulla metrica Rapporto di diagnostica (Dettaglio).

## <a name="filters"></a>Filtri

Nessuno. Non è possibile applicare filtri al Rapporto Dettagli conferenza.

## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni contenute nella sezione Informazioni conferenza del Rapporto Dettagli conferenza.

**Metriche Informazioni conferenza**


| **Nome**                 | **Descrizione**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **URI conferenza** <br/> | URI assegnato alla conferenza, ad esempio:  <br/> SIP: kmyer@litwareinc. com; GRUU; opaque = app: conf: Focus: ID: drg2y8v4  <br/> |
| **FQDN pool** <br/>      | Nome di dominio completo del pool di registrazione o del server perimetrale operativo in una sessione.  <br/>                             |
| **Ora di inizio** <br/>     | Data e ora di inizio della conferenza.  <br/>                                                                          |
| **Organizzatore** <br/>      | Indirizzo SIP dell'utente che ha organizzato la conferenza.  <br/>                                                               |
| **Ora di fine** <br/>       | Data e ora di fine della conferenza.  <br/>                                                                            |

La tabella seguente elenca le informazioni fornite nella sezione Partecipazione conferenza del Rapporto Dettagli conferenza.

**Metriche di Partecipazione conferenza**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Utente** <br/> |Indirizzo SIP dell'utente che ha partecipato alla conferenza.  <br/> |
|**Ruolo** <br/> |Ruolo, ad esempio Relatore, ricoperto dal partecipante alla conferenza.  <br/> |
|**Connettività** <br/> |Connettività di rete, solitamente Dall'interno o Dall'esterno, per il partecipante.  <br/> |
|**Ora partecipazione** <br/> |Data e ora in cui il partecipante si è unito alla conferenza.  <br/> |
|**Ora uscita** <br/> |Data e ora in cui il partecipante è uscito dalla conferenza.  <br/> |
|**Agente utente** <br/> |Identificatore del software utilizzato dall'endpoint del partecipante.  <br/> |
|**Rapporti di diagnostica** <br/> |Contiene informazioni relative alla diagnostica e alla risoluzione dei problemi, tra cui codici di risposta SIP, intestazioni di diagnostica, ore di partecipazione alla conferenza e ID diagnostica per le sessioni non riuscite.  <br/> |

Nella tabella seguente sono elencate le informazioni fornite nella sezione modalità conferenza del rapporto Dettagli conferenza.

**Metriche di Modalità conferenza**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Utente** <br/> |Indirizzo SIP dell'utente che ha partecipato alla conferenza.  <br/> |
|**Ora partecipazione** <br/> |Data e ora in cui il partecipante si è unito alla conferenza.  <br/> |
|**Ora uscita** <br/> |Data e ora in cui un partecipante è uscito dalla conferenza.  <br/> |
|**URI server per conferenze** <br/> |URI per il server per conferenze utilizzato nella conferenza.  <br/> |
|**Rapporti di diagnostica** <br/> |Contiene informazioni relative alla diagnostica e alla risoluzione dei problemi, tra cui codici di risposta SIP, intestazioni di diagnostica, ore di partecipazione alla conferenza e ID diagnostica per le sessioni non riuscite.  <br/> |


