---
title: Richiesta di certificato (Certificate Authority)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: "Quando si effettua una richiesta di certificato a un'Autorità di certificazione (CA) online (in genere server presenti nella rete interna) nella pagina Scelta dell'Autorità di certificazione, vengono visualizzate due opzioni:"
ms.openlocfilehash: 0081ab852a1650dfafd61471891a002be60def3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805326"
---
# <a name="certificate-request-certificate-authority"></a>Richiesta di certificato (Certificate Authority)
 
Quando si effettua una richiesta di certificato a un'Autorità di certificazione (CA) online (in genere server presenti nella rete interna) nella pagina **Scelta dell'Autorità di certificazione**, vengono visualizzate due opzioni:
  
1. Seleziona una CA dall'elenco rilevato nell'ambiente
    
2. Specifica un'altra autorità di certificazione
    
Se si seleziona la prima opzione, verrà visualizzato un elenco a discesa contenente tutte le autorità di certificazione basate su Windows Server rilevate nell'ambiente. Selezionare l'autorità di certificazione appropriata per il proprio certificato. Per tale scelta, potrebbe essere necessario consultarsi con l'amministratore CA.
  
Se si seleziona la seconda opzione, digitare il nome di dominio completo (FQDN) e l'istanza della CA da utilizzare per il certificato. Questa opzione è adatta se la CA che si desidera utilizzare non è basata su Windows Server, ma funzionerà per le CA basate su Windows Server.
  
> [!IMPORTANT]
> Accertarsi di appartenere ai gruppi necessari perché la richiesta del certificato abbia esito positivo. In genere, le autorità di certificazione hanno un requisito di autorizzazione diverso dai requisiti per l'installazione di Skype for Business Server nei server. Verificare i requisiti per richiedere il certificato con l'amministratore CA. 
  

