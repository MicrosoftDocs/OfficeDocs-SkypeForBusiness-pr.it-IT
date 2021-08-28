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
ms.localizationpriority: medium
description: Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
ms.openlocfilehash: 1b88ada924cbf2cf7f4153acda54584d81946cb0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579420"
---
# <a name="update-dns-srv-records"></a>Aggiornare i record SRV DNS

Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
  
In questo argomento viene descritto come aggiornare i record DNS (Domain Name System) dopo la migrazione a Skype for Business Server 2019. Dopo che tutti gli utenti sono stati spostati Skype for Business Server 2019, ma prima che il pool legacy o il Director venga disattivato, è necessario aggiornare i record DNS SRV nel DNS interno per ogni dominio SIP. Per questa procedura si presuppone che nel sistema DNS interno siano disponibili aree per i domini utente SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Per configurare un record DNS SRV

1. Nel server DNS fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.
    
2. Nell'albero della console per il dominio SIP espandere **Zone** di ricerca diretta, espandere il dominio SIP in cui è installato Skype for Business Server 2019 e passare all'impostazione **_tcp.** 
    
3. Nel riquadro destro fare clic con il pulsante destro **del** mouse _sipinternaltls e scegliere **Proprietà**.
    
4. In **Host offering this service** aggiornare il nome di dominio completo dell'host in modo che punti al pool Skype for Business Server 2019.
    
5. Fare clic su **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Per verificare che il nome di domino completo del pool Front End o del server Standard Edition possa essere risolto

1. Accedere a un computer client nel dominio.
    
2. Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.
    
3. Nella casella **Apri** digitare cmd e quindi fare clic su **OK.**
    
4. Al prompt dei comandi digitare nslookup _\<FQDN of the Front End pool\>_ o , quindi premere  _\<FQDN of the Standard Edition server\>_ INVIO.
    
5. Verificare di ricevere una risposta che si risolve nell'indirizzo IP appropriato per il nome FQDN.
    

