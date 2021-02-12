---
title: Configurare i record DNS per la distribuzione del pool pilota
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
description: Prima di distribuire il pool pilota, è necessario aggiornare le voci A dell'host DNS per il pool pilota. Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754056"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurare i record DNS per la distribuzione del pool pilota

Prima di distribuire il pool pilota, è necessario aggiornare le voci A dell'host DNS per il pool pilota. Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Per configurare i record A dell'host DNS

1. Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.
    
2. Nell'albero della console del dominio espandere **Zone** di ricerca diretta e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Skype for Business Server 2019.
    
3. Scegliere **Nuovo host (A o AAAA)**.
    
4. Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).
    
5. Fare **clic su Indirizzo IP** e quindi digitare l'indirizzo IP per il pool Front End.
    
6. Fare clic su **Aggiungi host** e quindi su **OK**. 
    
7. Al termine, scegliere **Fine**.
    

