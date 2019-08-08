---
title: Configurare i record DNS per la distribuzione del pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Prima di distribuire il pool pilota, è necessario aggiornare le voci dell'host DNS per il pool di piloti. Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.
ms.openlocfilehash: 0de8e144ea8d77e7ffa86562c120a54e3ec61ae0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239661"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurare i record DNS per la distribuzione del pool pilota

Prima di distribuire il pool di Pilot, è necessario aggiornare le voci dell'host DNS per il pool di piloti. Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Per configurare i record dell'host DNS

1. Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.
    
2. Nell'albero della console per il dominio espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Skype for Business Server 2019.
    
3. Fare clic su **nuovo host (A o AAAA)**.
    
4. Fare clic su **nome**, digitare il nome host per il pool di Skype for Business Server 2019 (il nome di dominio viene considerato dalla zona in cui è definito il record e non deve essere immesso come parte del record a).
    
5. Fare clic su **indirizzo IP**e quindi digitare l'indirizzo IP per il pool Front-end.
    
6. Fare clic su **Aggiungi host**e quindi su **OK**. 
    
7. Al termine, fare clic su **fine**.
    

