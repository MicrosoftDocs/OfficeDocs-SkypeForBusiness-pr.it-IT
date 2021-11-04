---
title: Espansione delle impostazioni di modifica del server perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'È possibile modificare le impostazioni per il server perimetrale o il pool di server perimetrali configurando le proprietà seguenti:'
ms.openlocfilehash: bb94c152fae183af3198f3fae99501ee33759bca
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765780"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Modificare l'espansione delle impostazioni del server perimetrale per Lync Server 2010
 
È possibile modificare le impostazioni per il server perimetrale o il pool di server perimetrali configurando le proprietà seguenti: 
  
 **Generale**
  
- **FQDN pool interno**: Il nome di dominio completo del pool interno è l'identità del server perimetrale o del pool di server perimetrali come definito nel record host DNS (A o AAAA per IPv6).
    
- Selezionare Abilita federazione per questo pool di server perimetrali **(porta 5061)** se si desidera abilitare il server perimetrale o il pool di server perimetrali per la federazione con altri partner del protocollo di avvio sessione.
    
    > [!IMPORTANT]
    > È possibile definire attivamente un solo server perimetrale o un pool di server perimetrali per la federazione. La configurazione mostrata nella schermata associata indica che un altro server perimetrale o un pool di server perimetrali è già configurato per la federazione. Il record SRV DNS esterno per la federazione (_sipfederationtls._tcp. ) punta al server perimetrale o al pool di server perimetrali \<external domain name\> per la federazione. 
  
- La porta di replica della configurazione interna **(HTTPS),** per impostazione predefinita alla porta TCP 4443, è la porta su cui viene replicata la copia locale (ovvero locale dei server perimetrali) dell'archivio di gestione centrale. La copia locale dell'archivio di gestione centrale si trova nel database **RTCLOCAL** nella SQL Server in ogni computer. La replica è unidirezionale, avviata dal server di gestione centrale (o dal Front End Server o dal pool Front End che detiene il ruolo server di gestione centrale) ai server perimetrali ed è una porta di interfaccia interna.
    
  **Selezione hop successivo**
  
- Selezionare nell'elenco il **Pool hop successivo**. È necessario definire un director, un pool di server Director, un Front End Server o un pool Front End per assumere questo ruolo. Il pool di hop successivo è il server o il pool di server che accetterà i messaggi SIP in ingresso dall'interfaccia interna del server perimetrale o del pool di server perimetrali e invierà SIP in uscita all'interfaccia interna del server perimetrale.
    
    > [!NOTE]
    > Il Director è un ruolo facoltativo e se si decide di non distribuire i Director, i Front End Server (singolo computer o pool) assumeranno il ruolo di Director. 
  
  **Impostazioni esterne**
  
Questa sezione delle proprietà consente di modificare le proprietà per le impostazioni esterne del server perimetrale o del pool di server perimetrali. È possibile modificare le proprietà seguenti:
  
- Selezionare la casella di controllo Abilita FQDN e indirizzo IP separati per conferenze Web e **A/V** se si desidera assegnare indirizzi IP e nomi di dominio completi distinti a ogni servizio server perimetrale.
    
    > [!NOTE]
    > Se non si seleziona la casella di controllo, è necessario usare porte distinte per ogni servizio Edge. Ogni servizio Edge condividerà il nome di dominio completo definito per il servizio Access Edge e utilizzerà quindi lo stesso indirizzo IP. Ogni servizio Edge deve essere identificato in modo univoco da un indirizzo IP distinto e dalla stessa porta oppure dallo stesso indirizzo IP e da valori di porta univoci. 
  
- Selezionare **Il servizio A/V Edge** è abilitato per NAT se si desidera configurare il servizio A/V Edge in modo che utilizzi un indirizzo privato o un altro indirizzo che verrà nascosto dietro un dispositivo NAT (Network Address Translation).
    
- Per modificare il servizio **Access Edge,** è necessario definire l'FQDN del pool per il servizio Access Edge come definito in DNS per host (A e AAAA se viene utilizzato IPv6) e un valore di porta 
    
- Per modificare il **servizio Web Conferencing Edge,** è necessario definire un FQDN del **pool** per il servizio Web Conferencing Edge come definito in DNS per host (A e AAAA se viene utilizzato IPv6) e un valore di porta
    
- Per modificare il **servizio A/V Edge,** è necessario definire un FQDN del **pool** per il servizio A/V Edge come definito in DNS da record host (A e AAAA se viene utilizzato IPv6) e un valore di porta
    
    > [!IMPORTANT]
    > Se è stata selezionata la casella di controllo Abilita FQDN e indirizzo IP separati per web conferencing e **A/V,** sarà disponibile per la modifica solo l'FQDN del pool di servizi Access Edge. Assegnare porte distinte a ognuno dei tre servizi Edge.
  
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  

