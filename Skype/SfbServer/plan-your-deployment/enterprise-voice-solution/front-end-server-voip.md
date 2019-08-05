---
title: Componenti VoIP del server front-end per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Informazioni sui componenti Enterprise Voice che si trovano nei server front-end in Skype for Business Server, incluso il servizio di traduzione e vari componenti di routing.
ms.openlocfilehash: d28beb809e172ea5d778e0cf8273cb232b7cf67c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187688"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Componenti VoIP del server front-end per Skype for Business Server

Informazioni sui componenti Enterprise Voice che si trovano nei server front-end in Skype for Business Server, incluso il servizio di traduzione e vari componenti di routing.

I componenti VoIP situati nei server front-end sono i seguenti:

- Servizio di traduzione

- Componente di routing in ingresso

- Componente di routing in uscita

- Componente di routing della messaggistica unificata di Exchange

- Componente di routing Intercluster

- [Componente Mediation Server in Skype for Business Server](mediation-server.md)

## <a name="translation-service"></a>Servizio di traduzione

Il servizio di traduzione è il componente server responsabile della traduzione di un numero composto nel formato E. 164 o in un altro formato, in base alle regole di normalizzazione definite dall'amministratore. Il servizio di traduzione può tradursi in formati diversi da E. 164 se l'organizzazione usa un sistema di numerazione privato o usa un gateway o un PBX che non supporta E. 164.

## <a name="inbound-routing-component"></a>Componente di routing in ingresso

Il componente di routing in ingresso gestisce le chiamate in arrivo in gran parte in base alle preferenze specificate dagli utenti nei client Voice aziendali. Facilita inoltre la chiamata del delegato e lo squillo simultaneo, se configurato dall'utente. Ad esempio, gli utenti specificano se le chiamate senza risposta vengono inoltrate o semplicemente registrate per la notifica. Se l'inoltro di chiamata è abilitato, gli utenti possono specificare se le chiamate senza risposta devono essere inoltrate a un altro numero o a un server di messaggistica unificata di Exchange configurato per fornire le risposte alle chiamate. Il componente di routing in ingresso viene installato per impostazione predefinita in tutti i server Standard Edition e front end.

## <a name="outbound-routing-component"></a>Componente di routing in uscita

Il componente di routing in uscita instrada le chiamate alle destinazioni PBX o PSTN. Applica le regole di autorizzazione della chiamata, come definito dal criterio vocale dell'utente, ai chiamanti e determina il gateway PSTN ottimale per il routing di ogni chiamata. Il componente di routing in uscita viene installato per impostazione predefinita in tutti i server Standard Edition e front end.

La logica di routing utilizzata dal componente di routing in uscita è in larga misura configurata dagli amministratori di rete o telefonici in base ai requisiti delle rispettive organizzazioni.

## <a name="exchange-um-routing-component"></a>Componente di routing della messaggistica unificata di Exchange

Il componente di routing della messaggistica unificata di Exchange gestisce il routing tra Skype for Business Server e i server che gestiscono la messaggistica unificata di Exchange per integrare Skype for Business Server con le caratteristiche di messaggistica unificata.

Il componente di routing della messaggistica unificata di Exchange gestisce anche il reinstradamento della segreteria telefonica tramite la rete PSTN se i server Messaggistica unificata di Exchange Se si hanno utenti di VoIP aziendale nei siti di succursale che non hanno un collegamento WAN resiliente a un sito centrale, l'appliance Survivable Branch distribuita nel sito della filiale offre la sopravvivenza della segreteria telefonica per gli utenti di Branch durante un'interruzione WAN. Quando il collegamento WAN non è disponibile, il Survivable Branch Appliance esegue le operazioni seguenti:

- reindirizza le chiamate senza risposta tramite la rete PSTN al server Messaggistica unificata di Exchange nel sito centrale

- consente a un utente di recuperare i messaggi della segreteria telefonica tramite la rete PSTN

- Accoda le notifiche delle chiamate perse e quindi le carica nel server Messaggistica unificata di Exchange quando viene ripristinato il collegamento WAN.

Per abilitare la reinstradazione della segreteria telefonica, è consigliabile che l'amministratore di Exchange configuri l'operatore automatico di messaggistica unificata di Exchange per accettare solo i messaggi.

Per informazioni dettagliate su queste caratteristiche, vedere integrazione e pianificazione della [messaggistica unificata di Exchange in locale](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) [per la resilienza di VoIP aziendale](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), rispettivamente.

## <a name="intercluster-routing-component"></a>Componente di routing Intercluster

Il componente di routing Intercluster è responsabile per il routing delle chiamate al pool di registrar principale del destinatario. Se non è disponibile, il componente instrada la chiamata al pool di registrar di backup del destinatario. Se i pool di registrar primari e di backup del destinatario non sono raggiungibili tramite la rete IP, il componente di routing Intercluster reindirizza la chiamata tramite PSTN al numero di telefono dell'utente.

## <a name="other-front-end-server-components-required-for-voip"></a>Altri componenti del server front-end necessari per VoIP

Altri componenti che risiedono nel server front-end o nel Director che offrono un supporto essenziale per VoIP, ma non sono componenti VoIP, includono i seguenti:

- **Servizi utente.** Eseguire la ricerca in numero inverso sul numero di telefono di destinazione di ogni chiamata in arrivo e corrispondere tale numero all'URI SIP dell'utente di destinazione. Usando queste informazioni, il componente di routing in ingresso distribuisce la chiamata agli endpoint SIP registrati di tale utente. Servizi utente è un componente principale in tutti i server e direttori front-end.

- **User Replicator.** Estrae i numeri di telefono degli utenti da servizi di dominio Active Directory e li scrive nelle tabelle del database RTC, dove sono disponibili per i servizi utente e per il server della Rubrica. User Replicator è un componente principale in tutti i server front-end.

- **Server Rubrica.** Fornisce informazioni sull'elenco indirizzi globale da servizi di dominio Active Directory ai client di Skype for Business Server. Recupera anche le informazioni relative a utenti e contatti dal database RTC, scrive le informazioni nei file della Rubrica e quindi archivia i file in una cartella condivisa in cui vengono scaricati dai client Skype for business. Il server della Rubrica scrive le informazioni nel database di RTCAb, usato dal servizio query Web della Rubrica per rispondere alle query di ricerca degli utenti da Skype for business mobile. Si normalizza facoltativamente i numeri di telefono degli utenti aziendali scritti nel database RTC allo scopo di provisionare i contatti degli utenti in Skype for business. Il servizio Rubrica viene installato per impostazione predefinita in tutti i server front-end. Il servizio query Web per la Rubrica viene installato per impostazione predefinita con i servizi Web di ogni server front-end.


