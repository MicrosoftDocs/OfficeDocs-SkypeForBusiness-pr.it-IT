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
ms.openlocfilehash: 5de1fc9204e22b30431f692770e3ec663599dd73
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768479"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype room System: licenza per il software Skype for business
 
Leggere questo argomento per informazioni su come verificare se si dispone di una licenza per il volume del software Skype for business. 
  
Skype room System usa un client Skype for business installato, che richiede una licenza per il volume del software. Prima di distribuire il primo sistema per la sala Skype, Scopri lo stato di licenza del volume della distribuzione usando i server di gestione delle chiavi (KMS) o le chiavi di attivazione multiple (MAK).
  
## <a name="key-management-servers-kms"></a>Server di gestione delle chiavi (KMS)

Se i KMS sono in posizione e distribuiscono le attivazioni di contratti multilicenza Skype for business, il sistema Skype room attiverà automaticamente il client Skype for business. Per scoprire se i KMS sono in posizione:
  
In un prompt dei comandi eseguire:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Per altre informazioni, vedere [come individuare gli host di Office e Windows KMS tramite DNS e rimuovere istanze non autorizzate](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Per configurare un KMS, vedere [attivazione di KMS da office 2013](https://technet.microsoft.com/library/ee624357.aspx) e [GVLKs per l'attivazione di KMS e Active Directory di Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Chiave di licenza per il volume generico di Office 2013 per Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (questa chiave fa sì che il sistema Skype room cerchi un KMS nella rete).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Più chiavi di attivazione (MAK) dal centro servizi Volume License (VLSC)

Se il cliente usa qualsiasi altro software per contratti multilicenza, il reparto IT gestirà le attivazioni software e il contratto multilicenza (VLA) usando il VLSC. Ciò consentirà inoltre alla società di acquistare le attivazioni di Skype for business VL, dopodiché la società può ottenere un MAK per l'input nella console di amministrazione di Skype room System.
  
Un cliente con un VLA deve conoscere le proprie credenziali di VLSC, che verranno usate per amministrare il contratto e ottenere MAK. Se non si è certi, il reparto Finanza del cliente dovrebbe essere in grado di verificare se il cliente ha pagato un VLA.
  
Per ottenere un MAK, accedere al centro servizi contratti multilicenza per visualizzare i contratti e scaricare i codici Product Key (MAK). Per altre informazioni, visitare il [centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK per Office 365 senza accesso VLSC

Se il cliente non ha un contratto multilicenza, le attivazioni di Skype for business saranno molto più difficili da gestire. Tuttavia, i clienti di Office 365 senza VLSC Access possono ottenere un MAK promozionale fornendo le informazioni seguenti all'OEM che vende il sistema Skype room System:
  
- Nome società
    
- Nome del contatto di distribuzione, posta elettronica e numero di telefono
    
- Numero di sistemi distribuiti
    
- Data di distribuzione
    
- Se il cliente ha un Technical Account Manager Microsoft, il nome e le informazioni di contatto del TAM
    

