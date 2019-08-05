---
title: Modificare il Expander delle impostazioni di Edge per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'È possibile modificare le impostazioni per il server perimetrale o il pool di Edge configurando le proprietà seguenti:'
ms.openlocfilehash: 1b349d5640ea2debb4730ce262795616258b3475
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189527"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Modificare il Expander delle impostazioni di Edge per Lync Server 2010
 
È possibile modificare le impostazioni per il server perimetrale o il pool di Edge configurando le proprietà seguenti: 
  
 **Generale**
  
- **FQDN del pool interno**: il nome di dominio completo del pool interno è l'identità del server perimetrale o del pool di Edge definito nel record DNS (Domain Name System) host (a o AAAA per IPv6).
    
- Selezionare **Abilita federazione per questo pool di bordi (porta 5061)** se si vuole abilitare l'Edge Server o il pool di Edge per la Federazione con altri partner del protocollo di avvio della sessione.
    
    > [!IMPORTANT]
    > È possibile definire un solo Edge Server o un pool di bordi attivamente per la Federazione. La configurazione visualizzata nella schermata associata indica che un altro Edge Server o un pool di Edge è già configurato per la Federazione. Record SRV DNS esterno per la Federazione (_sipfederationtls. _tcp.\< nome\>di dominio esterno) punterà al server perimetrale o al pool di Edge per la Federazione. 
  
- La **porta di replica della configurazione interna (HTTPS)**, per impostazione predefinita alla porta TCP 4443, è la porta in cui viene replicata la copia locale (ovvero locale per i server perimetrali) dell'archivio di gestione centrale. La copia locale di Central Management store si trova nel database **RTCLOCAL** in SQL Server in ogni computer. La replica è unidirezionale, avviata dal server di gestione centrale (oppure il front end server o il pool Front-end che contiene il ruolo del server di gestione centrale) agli Edge Server ed è una porta di interfaccia interna.
    
  **Selezione hop successivo**
  
- Selezionare per l'elenco il **pool di hop successivo**. Si definisce un Director, un pool di Director, un front end server o un pool Front end per assumere questo ruolo. Il pool di hop successivo è il pool di server o server che accetterà i messaggi SIP in ingresso dall'interfaccia interna del server perimetrale o del pool Edge e invierà il SIP in uscita all'interfaccia interna del bordo.
    
    > [!NOTE]
    > Il Director è un ruolo facoltativo e se si decide di non distribuire i direttori, i server front-end (singolo computer o pool) assumeranno il ruolo di Director. 
  
  **Impostazioni esterne**
  
Questa sezione delle proprietà consente di modificare le proprietà per le impostazioni esterne del server perimetrale o del pool di bordi. Le proprietà seguenti sono disponibili per la modifica:
  
- Selezionare la casella di controllo **attiva FQDN separato e indirizzo IP per le conferenze Web e a/V** se si vogliono assegnare indirizzi IP distinti e nomi di dominio completi a ogni servizio Edge Server.
    
    > [!NOTE]
    > Se si sceglie di non selezionare la casella di controllo, è necessario usare porte separate per ogni servizio Edge. Ogni servizio Edge condividerà l'FQDN definito per il servizio Access Edge e utilizzerà quindi lo stesso indirizzo IP. Ogni servizio Edge deve essere identificato in modo univoco da un indirizzo IP distinto e da una stessa porta oppure dagli stessi indirizzi IP e dai valori di porta univoci. 
  
- Selezionare **un/v Edge Server è abilitato NAT** se si vuole configurare il servizio a/v Edge per l'uso di un indirizzo privato o di un altro indirizzo che verrà nascosto dietro un dispositivo NAT (Network Address Translation).
    
- Per modificare il **servizio Access Edge**, è possibile definire il **nome di dominio completo del pool** per il servizio Access Edge definito in DNS per i record host (a e aaaa se IPv6 viene usato) e un valore di porta
    
- Per modificare il **servizio Web Conferencing Edge**, è possibile definire un **nome di dominio completo del pool** per il servizio Web Conferencing Edge definito in DNS per i record host (a e aaaa if IPv6 viene usato) e un valore di porta
    
- Per modificare il **servizio a/v Edge**, è possibile definire un **nome di dominio completo del pool** per il servizio a/v Edge definito in DNS per i record host (a e aaaa if IPv6 viene usato) e un valore di porta
    
    > [!IMPORTANT]
    > Se è stata selezionata la casella di controllo **Abilita FQDN separato e indirizzo IP per conferenze Web e a/V** , sarà disponibile solo il nome di dominio completo del pool di servizi Edge di Access per la modifica. Assegnare porte distinte per ognuno dei tre servizi Edge.
  
  **OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.
  
  **Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.
  
  **Guida** Consente di visualizzare questa schermata della Guida.
  

