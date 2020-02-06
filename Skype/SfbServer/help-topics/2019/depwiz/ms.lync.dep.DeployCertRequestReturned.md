---
title: Richiesta di certificato (restituito)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: "La pagina di stato della richiesta di certificato online presenta informazioni importanti che derivano dalla creazione e dall'emissione di una richiesta di certificato online. Questa pagina fornisce l'identificazione personale del certificato che identifica in modo univoco il certificato. Per impostazione predefinita, la casella di controllo assegna questo certificato agli usi dei certificati Skype for Business Server è selezionata. Se si fa clic su fine, il certificato verrà assegnato automaticamente a Skype for Business Server per gli scopi definiti durante la procedura di creazione della richiesta di certificato. Per impostazione predefinita, gli scopi che il certificato verrà assegnato sono i seguenti:"
ms.openlocfilehash: 1fce25992e6509fe10715f80f4121e08c6734be2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794295"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="d5cff-107">Richiesta di certificato (restituito)</span><span class="sxs-lookup"><span data-stu-id="d5cff-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="d5cff-108">La pagina di **stato della richiesta di certificato online** presenta informazioni importanti che derivano dalla creazione e dall'emissione di una richiesta di certificato online.</span><span class="sxs-lookup"><span data-stu-id="d5cff-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="d5cff-109">Questa pagina fornisce l'identificazione personale del certificato che identifica in modo univoco il certificato.</span><span class="sxs-lookup"><span data-stu-id="d5cff-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="d5cff-110">Per impostazione predefinita, la casella **di controllo assegna questo certificato agli usi dei certificati Skype for Business Server** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="d5cff-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="d5cff-111">Se si fa clic su **fine**, il certificato verrà assegnato automaticamente a Skype for Business Server per gli scopi definiti durante la procedura di creazione della richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="d5cff-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="d5cff-112">Per impostazione predefinita, gli scopi che il certificato verrà assegnato sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5cff-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="d5cff-113">Server predefinito per Mutual Transport Layer Security (MTLS)-connessioni ai client e ad altri server</span><span class="sxs-lookup"><span data-stu-id="d5cff-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="d5cff-114">Servizi Web interni-client e connessioni server nel sito servizi Web interni per Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="d5cff-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="d5cff-115">Servizi Web esterni-connessioni client e server nel sito servizi Web esterni per TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="d5cff-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="d5cff-116">Fare clic sulla **visualizzazione dei dettagli** del certificato per visualizzare il certificato per verificare che le proprietà del certificato siano quelle desiderate e che il certificato sia pronto per essere applicato e usato nel server.</span><span class="sxs-lookup"><span data-stu-id="d5cff-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="d5cff-117">Fare clic su **fine** per completare il processo di richiesta di certificato online.</span><span class="sxs-lookup"><span data-stu-id="d5cff-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="d5cff-118">Se è stata selezionata la casella **di controllo assegna questo certificato agli usi dei certificati Skype for Business Server**, il certificato verrà assegnato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d5cff-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="d5cff-119">Se si è scelto di deselezionare questa casella di controllo, è necessario assegnare il certificato in un passaggio separato.</span><span class="sxs-lookup"><span data-stu-id="d5cff-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d5cff-120">Se il certificato radice dell'autorità di certificazione (CA) emittente non si trova nell'archivio Autorità di certificazione radice attendibile del computer o se i certificati intermedi della CA non si trovano nell'archivio appropriato, verrà visualizzato lo stato di riepilogo, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="d5cff-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="d5cff-121">Non è possibile assegnare il certificato.</span><span class="sxs-lookup"><span data-stu-id="d5cff-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="d5cff-122">Per completare il processo di assegnazione del certificato, è necessario importare il certificato radice della CA emittente e gli eventuali certificati intermedi della CA e quindi assegnare il certificato facendo clic su **assegna** nella pagina della creazione guidata certificato principale.</span><span class="sxs-lookup"><span data-stu-id="d5cff-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

