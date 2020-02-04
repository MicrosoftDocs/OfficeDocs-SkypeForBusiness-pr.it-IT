---
title: Richiesta di certificato (Certificate Authority)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: "Quando si effettua una richiesta di certificato a un'Autorità di certificazione (CA) online (in genere server presenti nella rete interna) nella pagina Scegli Autorità di certificazione (CA), vengono visualizzate due opzioni:"
ms.openlocfilehash: 6cd2eb648897adc4c6d627f8c97659ce3b13ea4e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687809"
---
# <a name="certificate-request-certificate-authority"></a>Richiesta di certificato (Certificate Authority)
 
Quando si effettua una richiesta di certificato a un'Autorità di certificazione (CA) online (in genere server presenti nella rete interna) nella pagina **Scegli Autorità di certificazione (CA)**, vengono visualizzate due opzioni:
  
1. Seleziona una CA dall'elenco rilevato nell'ambiente
    
2. Specifica un'altra autorità di certificazione
    
Se si seleziona la prima opzione, verrà visualizzato un elenco a discesa contenente tutte le autorità di certificazione basate su Windows Server rilevate nell'ambiente. Selezionare l'autorità di certificazione appropriata per il proprio certificato. Per tale scelta, potrebbe essere necessario consultarsi con l'amministratore CA.
  
Se si seleziona la seconda opzione, digitare il nome di dominio completo (FQDN) e l'istanza della CA da utilizzare per il certificato. Questa opzione è adatta se la CA che si desidera utilizzare non è basata su Windows Server, ma funzionerà per le CA basate su Windows Server.
  
> [!IMPORTANT]
> Accertarsi di appartenere ai gruppi necessari perché la richiesta del certificato abbia esito positivo. In genere, le autorità di certificazione hanno un requisito di autorizzazione diverso dai requisiti per l'installazione di Skype for Business Server su server. Verificare i requisiti per richiedere il certificato con l'amministratore CA. 
  

