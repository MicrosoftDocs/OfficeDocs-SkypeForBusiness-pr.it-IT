---
title: Gestire le posizioni per i provider di servizi trunk SIP in Skype for Business Server
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Decisioni necessarie per pianificare un database di informazioni sulla posizione o un database esterno simile per una distribuzione di E9-1-1 con i provider di trunking SIP in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: aafe35f4978ac18897d11aa55f229df501d555ed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187637"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Gestire le posizioni per i provider di servizi trunk SIP in Skype for Business Server

Decisioni necessarie per pianificare un database di informazioni sulla posizione o un database esterno simile per una distribuzione di E9-1-1 con i provider di trunking SIP in Skype for Business Server VoIP aziendale.

Per configurare Skype for Business Server in modo da individuare automaticamente i client all'interno di una rete, è necessario popolare il database del servizio informazioni sulla posizione con una rete wiremap e pubblicare i percorsi oppure creare un collegamento a un database esterno che contiene già mapping corretti. Nell'ambito di questo processo devi convalidare gli indirizzi civici dei percorsi con il provider di servizi E9-1-1. Per informazioni dettagliate, vedere [configurare il database della posizione](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) nella documentazione relativa alla distribuzione.

Il database del servizio informazioni sulla posizione viene compilato con un percorso di risposta di emergenza (elfi), che è costituito da un indirizzo civico e dall'indirizzo specifico all'interno di un edificio. Il campo **percorso** del servizio informazioni posizione, ovvero la posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi). In tale lunghezza limitata, provare a includere le operazioni seguenti:

- Un nome di facile comprensione che identifica la posizione del chiamante di 911 per evitare che i soccorritori di emergenza trovino la posizione specifica subito quando arrivano all'indirizzo civico. Questo nome di posizione può includere un numero di edificio, un numero di piano, un designatore alare, un numero di camera e così via. Evitare i soprannomi noti solo ai dipendenti, in modo che i soccorritori di emergenza possano accedere alla posizione errata.

- Un identificatore di posizione che consente agli utenti di verificare facilmente che il client Skype for business abbia rilevato la posizione corretta. Il client Skype for business concatena automaticamente e visualizza la **posizione** e i campi della **città** individuati nella relativa intestazione. Una buona procedura consiste nell'aggiungere l'indirizzo di strada dell'edificio a ogni identificatore di posizione, ad esempio "primo piano <street number>". Senza l'indirizzo stradale, un identificatore di posizione generico come "primo piano" può essere applicato a qualsiasi edificio della città.

- Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è possibile aggiungere la parola **[near]** , ad esempio "near 1 ° piano 1234".

> [!NOTE]
> I percorsi aggiunti al database della posizione centrale non sono disponibili per il client finché non vengono pubblicati usando un comando di Skype for Business Server Management Shell e vengono replicati negli archivi locali del pool. Per informazioni dettagliate, vedere [pubblicazione del database della posizione](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) nella documentazione relativa alla distribuzione.

Nelle sezioni seguenti vengono illustrate le considerazioni che è necessario tenere in considerazione durante la compilazione e la gestione del database della posizione.

## <a name="populating-the-location-database"></a>Popolamento del database della posizione

Le domande seguenti consentono di determinare come popolare il database della posizione.

 **Quale processo verrà usato per popolare il database della posizione?**

Dove sono i dati e quali sono i passaggi da eseguire per convertire i dati nel formato richiesto dal database della posizione? Si aggiungono percorsi singolarmente o in blocco usando un file CSV?

 **Si dispone di un database di terze parti che contiene già una mappatura delle posizioni?**

Usando l'opzione servizio informazioni posizione secondaria per connettersi a un database di terze parti, è possibile raggruppare e gestire le posizioni usando una piattaforma offline. Un vantaggio per questo approccio è che, oltre ad associare le posizioni agli identificatori di rete, è possibile associare le posizioni a un utente. Ciò significa che il servizio informazioni sulla posizione può restituire più indirizzi, provenienti dal servizio informazioni sulla posizione secondaria, a un client Skype for business. L'utente può quindi scegliere la posizione più appropriata.

Per l'integrazione con il servizio informazioni sulla posizione, il database di terze parti deve seguire lo schema di richiesta/risposta della posizione del server Lync. Per informazioni dettagliate, vedere ["[MS-E911WS]: Web Service for E911 support Protocol Specification"](https://go.microsoft.com/fwlink/p/?linkid=213819). Per informazioni dettagliate sulla distribuzione di un servizio di informazioni sulla posizione secondaria, vedere [configurare un servizio di informazioni sulla posizione secondaria in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sulla compilazione del database della posizione, vedere [configurare il database della posizione](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) nella documentazione relativa alla distribuzione.

## <a name="maintaining-the-location-database"></a>Manutenzione del database della posizione

Dopo aver popolato il database della posizione, è necessario sviluppare una strategia per l'aggiornamento del database durante la modifica della configurazione della rete. Le domande seguenti consentono di determinare come gestire il database della posizione.

 **Come si aggiorna il database della posizione?**

Sono disponibili diversi scenari che richiedono un aggiornamento per il database della posizione, tra cui l'aggiunta di WAP, il ricablaggio di Office (con le diverse assegnazioni degli switch) e l'espansione della subnet. Si aggiorna direttamente ogni singola posizione o si esegue un aggiornamento in blocco di tutte le posizioni usando un file CSV?

 **Si utilizzerà un'applicazione SNMP per corrispondere agli indirizzi MAC client di Lync alla porta e agli identificatori di switch?**

Se si usa un'applicazione SNMP, è necessario sviluppare un processo manuale che contenga la coerenza tra l'applicazione SNMP e il database della posizione e le informazioni sulla porta. Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni sulla posizione non sarà in grado di restituire una posizione al client.


