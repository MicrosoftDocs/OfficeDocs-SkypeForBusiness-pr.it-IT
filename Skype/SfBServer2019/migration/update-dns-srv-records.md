---
title: Aggiornare i record SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.
ms.openlocfilehash: ef77f491efd090949ff5dd6b653dd3cd6ea1cde7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812774"
---
# <a name="update-dns-srv-records"></a>Aggiornare i record SRV DNS

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.
  
Questo argomento descrive come aggiornare i record DNS (Domain Name System) dopo la migrazione a Skype for Business Server 2019. Dopo che tutti gli utenti sono stati spostati in Skype for Business Server 2019, ma prima che il pool o il Director legacy venga disattivati, è necessario aggiornare i record SRV DNS nel DNS interno per ogni dominio SIP. Questa procedura presuppone che il DNS interno disponga di aree per i domini utente SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Per configurare un record SRV DNS

1. Nel server DNS fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.
    
2. Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**, espandere il dominio SIP in cui è installato Skype for Business Server 2019 e passare all'impostazione **_tcp** . 
    
3. Nel riquadro destro fare clic con il pulsante destro del mouse **_sipinternaltls** e scegliere **Proprietà**.
    
4. In **host che offre questo servizio**, aggiornare il nome di dominio completo dell'host per posizionare il puntatore sul pool di Skype for Business Server 2019.
    
5. Fare clic su **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Per verificare che il nome di dominio completo del pool Front-end o del server Standard Edition possa essere risolto

1. Accedere a un computer client nel dominio.
    
2. Fare clic sul pulsante **Start**e quindi su **Esegui**.
    
3. Nella casella **Apri** Digitare cmd e quindi fare clic su **OK**.
    
4. Al prompt dei comandi digitare il _ \<nome di dominio completo nslookup del pool\> di front end_ o _ \<il nome di\>dominio completo del server Standard Edition_, quindi premere INVIO.
    
5. Verificare di ricevere una risposta che venga risolta nell'indirizzo IP appropriato per il nome di dominio completo.
    

