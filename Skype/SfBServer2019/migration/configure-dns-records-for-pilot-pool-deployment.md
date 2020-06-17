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
description: Prima di distribuire il pool pilota, è necessario aggiornare le voci dell'host DNS A per il pool pilota. Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754056"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurare i record DNS per la distribuzione del pool pilota

Prima di distribuire il pool pilota, è necessario aggiornare l'host DNS A voci per il pool pilota. Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Per configurare i record A dell'host DNS

1. Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.
    
2. Nell'albero della console per il dominio, espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Skype for Business Server 2019.
    
3. Scegliere **Nuovo host (A o AAAA)**.
    
4. Fare clic su **nome**, digitare il nome host per il pool di Skype for Business Server 2019 (il nome di dominio viene assunto dall'area in cui il record è definito e non è necessario immetterlo come parte del record a).
    
5. Fare clic su **indirizzo IP**e quindi digitare l'indirizzo IP per il pool Front end.
    
6. Fare clic su **Aggiungi host** e quindi su **OK**. 
    
7. Al termine, scegliere **Fine**.
    

