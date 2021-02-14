---
title: Richiesta di certificato (Returned)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: "Nella pagina Stato richiesta certificato online vengono presentate informazioni importanti risultanti dalla creazione e dall'emissione della richiesta di certificato online. Viene fornita l'identificazione digitale del certificato che identifica in modo univoco il certificato. Per impostazione predefinita, la casella di controllo Assegna questo certificato agli utilizzi dei certificati di Skype for Business Server è selezionata. Se si fa clic su Fine, il certificato verrà assegnato automaticamente a Skype for Business Server per gli scopi definiti durante i passaggi di creazione della richiesta di certificato. Per impostazione predefinita, gli scopi per cui verrà assegnato il certificato sono i seguenti:"
ms.openlocfilehash: 8d7d1dc5013505b7874bccd2ee415f9211713e70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801836"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="a7d70-107">Richiesta di certificato (restituito)</span><span class="sxs-lookup"><span data-stu-id="a7d70-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="a7d70-108">Nella pagina **Stato richiesta certificato online** vengono presentate informazioni importanti risultanti dalla creazione e dall'emissione della richiesta di certificato online.</span><span class="sxs-lookup"><span data-stu-id="a7d70-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="a7d70-109">Viene fornita l'identificazione digitale del certificato che identifica in modo univoco il certificato.</span><span class="sxs-lookup"><span data-stu-id="a7d70-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="a7d70-110">Per impostazione predefinita, la casella di controllo Assegna questo certificato agli utilizzi dei certificati di **Skype for Business Server** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="a7d70-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="a7d70-111">Se si fa clic su **Fine,** il certificato verrà assegnato automaticamente a Skype for Business Server per gli scopi definiti durante i passaggi di creazione della richiesta di certificato.</span><span class="sxs-lookup"><span data-stu-id="a7d70-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="a7d70-112">Per impostazione predefinita, gli scopi per cui verrà assegnato il certificato sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7d70-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="a7d70-113">Server Default for Mutual Transport Layer Security (MTLS) - Connessioni a client e altri server</span><span class="sxs-lookup"><span data-stu-id="a7d70-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="a7d70-114">Servizi Web interni - Connessioni client e server nel sito dei servizi Web interni per TRANSPORT Layer Security/Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="a7d70-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="a7d70-115">Servizi Web esterni - Connessioni client e server nel sito dei servizi Web esterni per TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="a7d70-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="a7d70-116">Fare clic sul pulsante **Visualizza dettagli certificato** per visualizzare il certificato in modo da verificare che le relative proprietà siano quelle desiderate e che il certificato sia pronto per essere applicato e utilizzato nel server.</span><span class="sxs-lookup"><span data-stu-id="a7d70-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="a7d70-117">Fare clic su **Fine** per completare il processo di richiesta del certificato online.</span><span class="sxs-lookup"><span data-stu-id="a7d70-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="a7d70-118">Se è stata selezionata la casella di controllo Assegna questo certificato agli utilizzi dei certificati di **Skype for Business Server,** il certificato verrà assegnato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a7d70-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="a7d70-119">Se si è scelto di deselezionare questa casella di controllo, sarà necessario assegnare il certificato in un passaggio separato.</span><span class="sxs-lookup"><span data-stu-id="a7d70-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a7d70-120">Se il certificato radice dell'autorità di certificazione emittente non si trova nell'archivio dell'Autorità di certificazione radice attendibile del computer o se i certificati della CA intermedia non si trova nell'archivio appropriato, verrà visualizzato lo stato riepilogativo, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="a7d70-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="a7d70-121">Non si ha pertanto la possibilità di assegnare il certificato.</span><span class="sxs-lookup"><span data-stu-id="a7d70-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="a7d70-122">Per completare il processo di assegnazione del certificato, è perciò necessario importare il certificato radice della CA emittente e gli eventuali certificati della CA intermedia e quindi assegnarlo facendo clic su **Assegna** nella pagina principale della Configurazione guidata certificati.</span><span class="sxs-lookup"><span data-stu-id="a7d70-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

