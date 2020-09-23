---
title: Espansione delle impostazioni di modifica del server perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'È possibile modificare le impostazioni per il server perimetrale o il pool perimetrale configurando le proprietà seguenti:'
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216117"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni di modifica del server perimetrale per Lync Server 2010
 
È possibile modificare le impostazioni per il server perimetrale o il pool perimetrale configurando le proprietà seguenti: 
  
 **Generale**
  
- **FQDN del pool interno**: il nome di dominio completo del pool interno è l'identità del server perimetrale o del pool perimetrale come definito nel record host DNS (Domain Name System) (a o AAAA per IPv6).
    
- Selezionare **Abilita federazione per questo pool di server perimetrali (porta 5061)** se si desidera abilitare l'Edge o il pool di Edge per la Federazione con altri partner del protocollo di avvio della sessione.
    
    > [!IMPORTANT]
    > È possibile definire un solo server perimetrale o un pool di perimetri attivamente per la Federazione. La configurazione mostrata nella schermata associata indica che un altro server perimetrale o un pool perimetrale è già configurato per la Federazione. Il record DNS SRV esterno per la Federazione (_sipfederationtls. _tcp.) punterà \<external domain name\> al server perimetrale o al pool perimetrale per la Federazione. 
  
- La **porta di replica della configurazione interna (HTTPS)**, per impostazione predefinita nella porta TCP 4443, è la porta in cui viene replicata la copia locale (ovvero locale per i server perimetrali) dell'archivio di gestione centrale. La copia locale dell'archivio di gestione centrale è presente nel database di **RTCLOCAL** in SQL Server in ogni computer. La replica è unidirezionale, avviata dal server di gestione centrale (o il front end server o il pool Front end che contiene il ruolo del server di gestione centrale) ai server perimetrali ed è una porta dell'interfaccia interna.
    
  **Selezione hop successivo**
  
- Selezionare nell'elenco il **Pool hop successivo**. È possibile definire un Director, un pool di server Director, un front-end o un pool Front end per assumere questo ruolo. Il pool di hop successivo è il server o il pool di server che accetterà i messaggi SIP in ingresso dall'interfaccia interna del server perimetrale o del pool perimetrale e invierà SIP in uscita all'interfaccia interna del perimetro.
    
    > [!NOTE]
    > Il Director è un ruolo facoltativo e, se si decide di non distribuire i Director, i Front End Server (singolo computer o pool) assumeranno il ruolo di amministratore. 
  
  **Impostazioni esterne**
  
Questa sezione delle proprietà consente di modificare le proprietà per le impostazioni esterne del server perimetrale o del pool di Edge. È possibile modificare le proprietà seguenti:
  
- Selezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e a/V** se si desidera assegnare indirizzi IP distinti e nomi di dominio completi a ogni servizio server perimetrale.
    
    > [!NOTE]
    > Se non si seleziona la casella di controllo, è necessario usare porte distinte per ogni servizio Edge. Ogni servizio Edge condividerà il nome di dominio completo definito per il servizio Access Edge e utilizzerà lo stesso indirizzo IP. Ogni servizio Edge deve essere identificato in modo univoco da un indirizzo IP distinto e dalla stessa porta oppure dallo stesso indirizzo IP e da valori di porta univoci. 
  
- Selezionare il **servizio a/v Edge è abilitato NAT** se si desidera configurare il servizio a/v Edge per l'utilizzo di un indirizzo privato o di un altro indirizzo che sarà nascosto dietro un dispositivo NAT (Network Address Translation).
    
- Per modificare il **servizio Access Edge**, è possibile definire l' **FQDN del pool** per il servizio Access Edge come definito in DNS da record host (a e aaaa se viene usato IPv6) e da un valore di porta
    
- Per modificare il **servizio Web Conferencing Edge**, è possibile definire un **FQDN del pool** per il servizio Web Conferencing Edge come definito in DNS dai record host (a e aaaa se viene usato IPv6) e da un valore di porta
    
- Per modificare il **servizio a/v Edge**, è possibile definire un **FQDN del pool** per il servizio a/v Edge come definito in DNS da record host (a e aaaa se viene usato IPv6) e da un valore di porta
    
    > [!IMPORTANT]
    > Se è stata selezionata la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e a/V** , solo il nome FQDN del pool di servizi Access Edge sarà disponibile per la modifica. Assegnare porte distinte a ognuno dei tre servizi Edge.
  
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  

