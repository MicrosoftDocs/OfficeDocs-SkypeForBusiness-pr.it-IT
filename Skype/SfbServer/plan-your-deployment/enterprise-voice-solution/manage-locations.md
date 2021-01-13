---
title: Gestire le posizioni per i provider di servizi trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Le decisioni necessarie per la pianificazione di un database delle informazioni sulla posizione o di un database esterno simile per una distribuzione di E9-1-1 utilizzando i provider di trunking SIP, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 9918fc2cb6bc9d05166d648ab3285a964d15f290
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825436"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Gestire le posizioni per i provider di servizi trunk SIP in Skype for Business Server

Le decisioni necessarie per la pianificazione di un database delle informazioni sulla posizione o di un database esterno simile per una distribuzione di E9-1-1 utilizzando i provider di trunking SIP, in Skype for Business Server VoIP aziendale.

Per configurare Skype for Business Server in modo da individuare automaticamente i client all'interno di una rete, è necessario popolare il database del servizio informazioni percorso con una rete wiremap e pubblicare i percorsi oppure collegarsi a un database esterno che già contiene i mapping corretti. Come parte di questo processo, è necessario convalidare gli indirizzi civici dei percorsi con il provider di servizi E9-1-1. Per ulteriori informazioni, vedere [Configure the location database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) nella documentazione relativa alla distribuzione.

È possibile popolare il database del servizio informazioni percorso con un percorso di risposta di emergenza, che è costituito da un indirizzo civico e dall'indirizzo specifico all'interno di un edificio. Il **campo percorso del servizio informazioni** percorso, che corrisponde alla posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi). Tentare di includere, in tale lunghezza, gli elementi seguenti:

- Un nome di facile comprensione che identifichi la posizione del chiamante del servizio di emergenza (911), per consentire agli addetti del servizio di emergenza di trovare immediatamente la posizione specifica quando si recano all'indirizzo. Questo nome di posizione può includere il numero di edificio, l'indicazione della scala, il numero del piano, il numero di porta e così via. Evitare nomi alternativi noti solo ai dipendenti, che potrebbero indirizzare gli addetti del servizio di emergenza nel posto sbagliato.

- Un identificatore di percorso che aiuta gli utenti a vedere facilmente che il client Skype for business ha raccolto la posizione corretta. Il client Skype for business consente di concatenare e visualizzare automaticamente i campi **località** e **città** individuati nell'intestazione. Una buona procedura consiste nell'aggiungere l'indirizzo civico dell'edificio a ogni identificatore di posizione (ad esempio, "1st floor <street number> "). Se non viene specificato l'indirizzo, un identificatore di posizione generico come "1° piano" potrebbe riferirsi a qualsiasi edificio della città.

- Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è possibile aggiungere la parola **[near]** (ad esempio, "Near 1st floor 1234").

> [!NOTE]
> I percorsi aggiunti al database delle posizioni centrali non sono disponibili per il client finché non vengono pubblicati utilizzando un comando di Skype for Business Server Management Shell e vengono replicati negli archivi locali del pool. Per informazioni dettagliate, vedere [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) nella documentazione relativa alla distribuzione.

Nelle sezioni seguenti vengono illustrate le considerazioni che è necessario prendere in considerazione durante la compilazione e la gestione del database delle posizioni.

## <a name="populating-the-location-database"></a>Popolamento del database delle posizioni

Le domande seguenti possono essere utili per determinare come popolare il database delle posizioni.

 **Valutare quale processo verrà utilizzato per popolare il database delle posizioni.**

Esaminare dove si trovano i dati e quali operazioni è necessario eseguire per convertirli nel formato richiesto dal database delle posizioni. Considerare inoltre se le posizioni verranno aggiunte singolarmente o in gruppo tramite un file CSV.

 **Valutare se si dispone di un database di terze parti contenente già un mapping di posizioni.**

Se si utilizza l'opzione servizio informazioni percorso secondario per connettersi a un database di terze parti, è possibile raggruppare e gestire percorsi tramite una piattaforma offline. Uno dei vantaggi di questo approccio è che le posizioni possono essere associate non solo a identificatori di rete, ma anche a un utente. Questo significa che il servizio informazioni percorso può restituire più indirizzi, provenienti dal servizio informazioni percorso secondario, a un client Skype for business. L'utente può quindi scegliere la posizione più appropriata.

Per l'integrazione con il servizio informazioni percorso, è necessario che il database di terze parti segua lo schema di richiesta/risposta percorso di Lync Server. Per informazioni dettagliate, vedere  ["[MS-E911WS]: servizio Web per la specifica del protocollo di supporto di E911"](https://go.microsoft.com/fwlink/p/?linkid=213819). Per informazioni dettagliate sulla distribuzione di un servizio di informazioni sul percorso secondario, vedere [Configure a Secondary Location Information Service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate su come popolare il database delle posizioni, vedere [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) nella documentazione relativa alla distribuzione.

## <a name="maintaining-the-location-database"></a>Gestione del database delle posizioni

Dopo aver popolato il database delle posizioni, è necessario sviluppare una strategia per aggiornarlo in base alle modifiche di configurazione della rete. Le considerazioni seguenti possono essere utili per determinare come verrà gestito il database delle posizioni.

 **Valutare come verrà aggiornato il database delle posizioni.**

Sono disponibili diversi scenari che richiedono un aggiornamento al database delle posizioni, tra cui l'aggiunta di WAP, il ricablaggio di Office (con l'assegnazione di diverse assegnazioni di switch) e l'espansione della subnet. Considerare se si prevede di aggiornare direttamente ogni singola posizione o di eseguire un aggiornamento in blocco delle posizioni mediante un file CSV.

 **Considerare se verrà utilizzata un'applicazione SNMP per creare una corrispondenza tra gli indirizzi MAC dei client Lync e gli identificatori di porte e commutatori,**

Se si utilizza un'applicazione SNMP, è necessario sviluppare un processo manuale per mantenere la coerenza a livello di informazioni su porte e chassis dei commutatori tra l'applicazione SNMP e il database delle posizioni. Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni percorso non sarà in grado di restituire un percorso al client.


