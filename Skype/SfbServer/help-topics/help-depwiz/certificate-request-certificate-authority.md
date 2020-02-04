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
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="f64ee-103">Richiesta di certificato (Certificate Authority)</span><span class="sxs-lookup"><span data-stu-id="f64ee-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="f64ee-104">Quando si effettua una richiesta di certificato a un'Autorità di certificazione (CA) online (in genere server presenti nella rete interna) nella pagina **Scegli Autorità di certificazione (CA)**, vengono visualizzate due opzioni:</span><span class="sxs-lookup"><span data-stu-id="f64ee-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="f64ee-105">Seleziona una CA dall'elenco rilevato nell'ambiente</span><span class="sxs-lookup"><span data-stu-id="f64ee-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="f64ee-106">Specifica un'altra autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="f64ee-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="f64ee-107">Se si seleziona la prima opzione, verrà visualizzato un elenco a discesa contenente tutte le autorità di certificazione basate su Windows Server rilevate nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f64ee-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="f64ee-108">Selezionare l'autorità di certificazione appropriata per il proprio certificato.</span><span class="sxs-lookup"><span data-stu-id="f64ee-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="f64ee-109">Per tale scelta, potrebbe essere necessario consultarsi con l'amministratore CA.</span><span class="sxs-lookup"><span data-stu-id="f64ee-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="f64ee-p102">Se si seleziona la seconda opzione, digitare il nome di dominio completo (FQDN) e l'istanza della CA da utilizzare per il certificato. Questa opzione è adatta se la CA che si desidera utilizzare non è basata su Windows Server, ma funzionerà per le CA basate su Windows Server.</span><span class="sxs-lookup"><span data-stu-id="f64ee-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f64ee-112">Accertarsi di appartenere ai gruppi necessari perché la richiesta del certificato abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f64ee-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="f64ee-113">In genere, le autorità di certificazione hanno un requisito di autorizzazione diverso dai requisiti per l'installazione di Skype for Business Server su server.</span><span class="sxs-lookup"><span data-stu-id="f64ee-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="f64ee-114">Verificare i requisiti per richiedere il certificato con l'amministratore CA.</span><span class="sxs-lookup"><span data-stu-id="f64ee-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

