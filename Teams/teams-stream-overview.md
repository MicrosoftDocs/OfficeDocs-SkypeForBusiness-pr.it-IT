---
title: Panoramica del codificatore per lo streaming in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Questo articolo offre una panoramica della configurazione RTMP basata su codificatore per gli eventi di streaming di Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d7ea21edb6677397785367cecd3daaf9bbe513f3
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767942"
---
# <a name="live-streaming-events-in-microsoft-teams"></a>Eventi in streaming live in Microsoft Teams

È possibile creare eventi live usando Microsoft Teams nell'intera organizzazione. È possibile pianificare, produrre e fornire eventi live per vari scenari, ad esempio eventi a livello aziendale, aggiornamenti dei dirigenti e altro ancora. Gli eventi di live streaming consentono ai produttori di curare e controllare il contenuto trasmesso a un pubblico.

È possibile creare, pianificare ed eseguire eventi live usando un unico flusso RTMP o RTMPS a bitrate da un codificatore. Ci occuperemo di tutta la transcodifica per il recapito a bitrate adattivo ai vostri spettatori.

Proprio come qualsiasi altro video in Teams, è possibile rendere l'evento live aperto all'intera azienda o limitare l'accesso a gruppi specifici. Ciò offre un'esperienza di creazione e visualizzazione end-to-end all'interno di Teams.

Dopo l'evento, il video sarà disponibile su richiesta con funzionalità intelligenti tra cui:

- Sintesi vocale e sottotitoli.
- La ricerca della trascrizione e i codici temporali ti consentono di trovare rapidamente i momenti importanti in un video.

## <a name="live-events-in-microsoft-365"></a>Eventi live in Microsoft 365

È possibile creare un evento live steaming in Teams o Yammer, ovunque si trovi il pubblico, il team o la community. I partecipanti possono guardare l'evento in video ad alta definizione (HD) e inviare domande tramite un'esperienza Q&A moderata. Una perfetta integrazione in Microsoft 365 significa che è possibile usare Teams per offrire eventi di qualità studio altamente prodotti.

## <a name="get-started"></a>Per iniziare

Assicurarsi che agli utenti che si vuole essere in grado di creare eventi live siano concesse le autorizzazioni necessarie per creare un evento live. Per impostazione predefinita, tutti gli utenti dell'organizzazione possono creare un evento live, tuttavia un amministratore di Teams può limitare l'accesso. Altre informazioni sull'amministrazione di eventi live.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams, passare a **Criteri** > **per gli eventi in tempo** reale > scheda **Gestisci criteri** .
1. Se vuoi:
    1. modificare il criterio predefinito esistente, scegliere **Globale (impostazione predefinita a livello di organizzazione).Edit the existing default policy, choose Global (Org-wide default)**.
    1. creare un nuovo criterio personalizzato, scegliere **+Aggiungi**.
    1. modificare un criterio personalizzato, selezionarne uno e quindi scegliere **Modifica**.

## <a name="monitor-your-event"></a>Monitorare l'evento

Come produttore, è possibile usare il client di Teams per visualizzare il feed del pubblico (visibile sul lato destro) e il numero di partecipanti che stanno visualizzando l'evento.

## <a name="capabilities"></a>Capacità

Di seguito sono indicate le funzionalità degli eventi di streaming live:

|Operazione                                            |Limiti                                                               |
|-----------------------------------------------------|---------------------------------------------------------------------|
|Creare eventi live in Teams (con codificatore esterno)  |Enterprise (E1, E3, E5), Education (A3, A5)                          |
|Guarda l'evento live                                     |Visualizzatori con autorizzazioni per visualizzare l'evento e una licenza di Teams valida (a meno che l'evento non sia pubblico, non è necessaria una licenza da visualizzare) |
|Risoluzione massima                                   |720p                                                                 |
|Numero massimo di eventi live simultanei (pre-live o live) |15                                                                   |
|Visualizzatori simultanei attivi                            |10000                                                                |
|Durata massima dell'evento live                         |4 ore                                                              |
|Supporto per la memorizzazione nella cache della rete partner                      |Hive, Kolletive, Riverbed, Ramp, Microsoft                          |
|Altro supporto per la memorizzazione nella cache di rete                        |Può funzionare, ma non è supportato                                        |
|Controlli DVR partecipanti                                |Pausa, velocità di riproduzione (2x recupero, 1x in tempo reale), cerca                |
|Sottotitoli in tempo reale                                   |708 caption pass-through dal codificatore                                |
|Sintesi vocale automatica e didascalie                |Elaborato dopo l'evento                                            |
|Discussioni interattive                              |Supportata da Yammer quando l'evento viene creato da Yammer           |
|Commenti di Teams                                       |Disponibile al termine dell'evento                                       |
|Visualizzazione su richiesta su evento live (dopo evento)        |Transizione automatica da live a on demand per la visualizzazione e l'indicizzazione immediate in Teams |
|Registrazione scaricabile                               |Elaborato e disponibile dopo l'evento live dai proprietari               |

Gli eventi live in Teams sono un servizio altamente disponibile e ci si può aspettare buone prestazioni su vasta scala. Nell'improbabile scenario che comporta la necessità di un failover, gli eventi live che usano la codifica esterna non avranno ridondanza e non saranno ripristinabili.
