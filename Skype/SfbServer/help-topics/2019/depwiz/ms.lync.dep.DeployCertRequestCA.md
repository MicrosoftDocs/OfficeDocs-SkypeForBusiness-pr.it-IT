---
title: Richiesta di certificato (Certificate Authority)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: "Quando si effettua una richiesta di certificato a un'Autorità di certificazione (CA) online (in genere server presenti nella rete interna) nella pagina Scelta dell'Autorità di certificazione, vengono visualizzate due opzioni:"
ms.openlocfilehash: 032e0f91050000c354e77ec853da569befa291c2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832810"
---
# <a name="certificate-request-certificate-authority"></a>Richiesta di certificato (Certificate Authority)
 
Quando si effettua una richiesta di certificato a un'Autorità di certificazione (CA) online (in genere server presenti nella rete interna) nella pagina **Scelta dell'Autorità di certificazione**, vengono visualizzate due opzioni:
  
1. Seleziona una CA dall'elenco rilevato nell'ambiente
    
2. Specifica un'altra autorità di certificazione
    
Se si seleziona la prima opzione, verrà visualizzato un elenco a discesa contenente tutte le Windows di certificazione basate su server rilevate nell'ambiente. Selezionare l'autorità di certificazione appropriata per il proprio certificato. Per tale scelta, potrebbe essere necessario consultarsi con l'amministratore CA.
  
Se si seleziona la seconda opzione, digitare il nome di dominio completo (FQDN) e l'istanza della CA da utilizzare per il certificato. Questa opzione è adatta se la CA che si desidera utilizzare non è basata su Windows Server, ma funzionerà per le CA basate su Windows Server.
  
> [!IMPORTANT]
> Accertarsi di appartenere ai gruppi necessari perché la richiesta del certificato abbia esito positivo. In genere, le autorità di certificazione hanno un requisito di autorizzazione diverso dai requisiti per l'Skype for Business Server nei server. Verificare i requisiti per richiedere il certificato con l'amministratore CA. 
  

