---
title: Aggiornare i record SRV DNS
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753268"
---
# <a name="update-dns-srv-records"></a>Aggiornare i record SRV DNS

Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
  
In questo argomento viene descritto come aggiornare i record DNS (Domain Name System) dopo la migrazione a Skype for Business Server 2019. Dopo che tutti gli utenti sono stati spostati in Skype for Business Server 2019, ma prima che il pool o il Director legacy venga rimosso, è necessario aggiornare i record DNS SRV nel DNS interno per ogni dominio SIP. Per questa procedura si presuppone che nel sistema DNS interno siano disponibili aree per i domini utente SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Per configurare un record DNS SRV

1. Nel server DNS fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.
    
2. Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**, espandere il dominio SIP in cui è installato Skype for Business Server 2019 e passare all'impostazione **_tcp** . 
    
3. Nel riquadro destro fare clic con il pulsante destro del mouse su **_sipinternaltls** e scegliere **Proprietà**.
    
4. In **host che offre questo servizio**aggiornare il nome di dominio completo host in modo che punti al pool di Skype for Business Server 2019.
    
5. Fare clic su **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Per verificare che il nome di domino completo del pool Front End o del server Standard Edition possa essere risolto

1. Accedere a un computer client nel dominio.
    
2. Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.
    
3. Nella casella **Apri** Digitare cmd e quindi fare clic su **OK**.
    
4. Al prompt dei comandi digitare nslookup _\<FQDN of the Front End pool\>_ o _\<FQDN of the Standard Edition server\>_ , quindi premere INVIO.
    
5. Verificare di ricevere una risposta che si risolve nell'indirizzo IP appropriato per il nome FQDN.
    

