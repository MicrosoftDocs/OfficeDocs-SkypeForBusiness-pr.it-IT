---
title: Licenza software Skype for business per Skype room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leggere questo argomento per informazioni su come verificare se si dispone di una licenza per il volume del software Skype for business.
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220926"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype room System: licenza del software Skype for business
 
Leggere questo argomento per informazioni su come verificare se si dispone di una licenza per il volume del software Skype for business. 
  
Skype room System utilizza un client Skype for business installato, che richiede una licenza per il volume del software. Prima di distribuire il primo sistema di Skype room, individuare lo stato di licenza del volume della distribuzione, utilizzando i server di gestione delle chiavi (KMS) o più chiavi di attivazione (MAK).
  
## <a name="key-management-servers-kms"></a>Server di gestione delle chiavi (KMS)

Se i KMS sono sul posto e distribuiscono le attivazioni con contratti multilicenza di Skype for business, il sistema Skype room attiverà automaticamente il client Skype for business. Per sapere se il servizio di gestione delle chiavi è sul posto:
  
Da un prompt dei comandi eseguire:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Per ulteriori informazioni, vedere [come individuare gli host del servizio di gestione delle chiavi di Office e Windows tramite DNS e rimuovere le istanze non autorizzate](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Per impostare un servizio di gestione delle chiavi, vedere l' [attivazione del servizio di gestione delle chiavi di office 2013](https://technet.microsoft.com/library/ee624357.aspx) e [GVLK for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Chiave per contratti multilicenza di Office 2013 generici per Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (questa chiave causa la ricerca di un servizio di gestione delle chiavi in una rete in Skype room System).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Tasti di attivazione multipli (MAK) dal centro servizi per contratti multilicenza (VLSC)

Se il cliente utilizza qualsiasi altro software per contratti multilicenza, il reparto IT gestirà le attivazioni software e il contratto multilicenza (VLA) utilizzando VLSC. Ciò consentirà anche all'azienda di acquistare le attivazioni di Skype for business VL, dopo di che la società può ottenere un MAK per l'input nella console di amministrazione di Skype room System.
  
Un cliente con un VLA deve conoscere le credenziali di VLSC, che verranno utilizzate per amministrare il contratto e ottenere MAK. Se non si è certi, il reparto Finanze del cliente dovrebbe essere in grado di confermare se il cliente ha pagato un VLA.
  
Per ottenere un MAK, accedere a Volume Licensing Service Center per visualizzare i contratti e scaricare i codici Product Key (MAK). Per ulteriori informazioni, visitare il [centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK per Microsoft 365 o Office 365 senza accesso di VLSC

Se il cliente non ha un contratto multilicenza, le attivazioni di Skype for business saranno molto più difficili da gestire. Tuttavia, i clienti di Microsoft 365 e Office 365 senza l'accesso di VLSC possono ottenere un MAK promozionale fornendo le seguenti informazioni all'OEM che vende il sistema della sala Skype:
  
- Nome della società
    
- Nome del contatto di distribuzione, posta elettronica e numero di telefono
    
- Numero di sistemi distribuiti
    
- Data di distribuzione
    
- Se il cliente ha un responsabile dell'account tecnico Microsoft, il nome e le informazioni di contatto del TAM
    

