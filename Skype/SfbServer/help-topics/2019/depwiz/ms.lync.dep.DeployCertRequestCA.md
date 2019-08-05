---
title: Richiesta di certificato (Certificate Authority)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: "Quando si effettua una richiesta di certificato a un'Autorità di certificazione (CA) online (in genere server presenti nella rete interna) nella pagina Scegli Autorità di certificazione (CA), vengono visualizzate due opzioni:"
ms.openlocfilehash: 755d18895d5642752188455938216392a3b52fe0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191429"
---
# <a name="certificate-request-certificate-authority"></a>Richiesta di certificato (Certificate Authority)
 
Quando si effettua una richiesta di certificato a un'Autorità di certificazione (CA) online (in genere server presenti nella rete interna) nella pagina **Scegli Autorità di certificazione (CA)**, vengono visualizzate due opzioni:
  
1. Seleziona una CA dall'elenco rilevato nell'ambiente
    
2. Specifica un'altra autorità di certificazione
    
Se si seleziona la prima opzione, verrà visualizzato un elenco a discesa contenente tutte le autorità di certificazione basate su Windows Server rilevate nell'ambiente. Selezionare l'autorità di certificazione appropriata per il proprio certificato. Per tale scelta, potrebbe essere necessario consultarsi con l'amministratore CA.
  
Se si seleziona la seconda opzione, digitare il nome di dominio completo (FQDN) e l'istanza della CA da utilizzare per il certificato. Questa opzione è adatta se la CA che si desidera utilizzare non è basata su Windows Server, ma funzionerà per le CA basate su Windows Server.
  
> [!IMPORTANT]
> Accertarsi di appartenere ai gruppi necessari perché la richiesta del certificato abbia esito positivo. In genere, le autorità di certificazione hanno un requisito di autorizzazione diverso dai requisiti per l'installazione di Skype for Business Server su server. Verificare i requisiti per richiedere il certificato con l'amministratore CA. 
  

