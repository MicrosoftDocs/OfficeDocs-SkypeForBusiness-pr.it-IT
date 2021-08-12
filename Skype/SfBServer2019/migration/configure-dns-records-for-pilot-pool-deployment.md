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
description: Prima di distribuire il pool pilota, è necessario aggiornare le voci A host DNS per il pool pilota. Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
ms.openlocfilehash: 270b0bda7da679cb0c75e9a99e10a898dcee6ac70413ce276abfe19ba1eb2231
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337834"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurare i record DNS per la distribuzione del pool pilota

Prima di distribuire il pool pilota, è necessario aggiornare le voci A dell'host DNS per il pool pilota. Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Per configurare i record A dell'host DNS

1. Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.
    
2. Nell'albero della console del dominio espandere **Zone** di ricerca diretta e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Skype for Business Server 2019.
    
3. Scegliere **Nuovo host (A o AAAA)**.
    
4. Fare clic su Nome , digitare il nome host per il pool di Skype for Business Server 2019 (il nome di dominio viene considerato dalla zona in cui è definito il record e non deve essere immesso come parte del record A).
    
5. Fare **clic su Indirizzo IP** e quindi digitare l'indirizzo IP per il pool Front End.
    
6. Fare clic su **Aggiungi host** e quindi su **OK**. 
    
7. Al termine, scegliere **Fine**.
    

