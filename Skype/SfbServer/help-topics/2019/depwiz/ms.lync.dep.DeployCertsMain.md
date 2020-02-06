---
title: Configurazione guidata certificati
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: NOINDEX, NOFOLLOW
description: Per richiedere, assegnare, rimuovere o visualizzare i certificati, è possibile utilizzare la Configurazione guidata certificati. A tale scopo, è necessario essere connessi come membri del gruppo RTCUniversalServerAdmins. Per richiedere un certificato a un'Autorità di certificazione (CA) pubblica, non è necessario appartenere ad altri gruppi. Per richiedere un certificato dall'infrastruttura a chiave pubblica (PKI) dell'organizzazione, è necessario confermare le altre appartenenze ai gruppi di cui si ha bisogno. Durante l'attività di richiesta, è possibile immettere credenziali alternative che verranno usate per richiedere il certificato dalla CA emittente della PKI.
ms.openlocfilehash: 4a36026f1dd79bbee591ba48158675adfc9455f5
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796105"
---
# <a name="certificate-wizard"></a><span data-ttu-id="885bf-107">Configurazione guidata certificati</span><span class="sxs-lookup"><span data-stu-id="885bf-107">Certificate Wizard</span></span>
 
<span data-ttu-id="885bf-108">Per \*\*\*\* richiedere, \*\*\*\* assegnare, \*\*\*\* rimuovere o \*\*\*\* visualizzare i certificati, è possibile utilizzare la Configurazione guidata certificati.</span><span class="sxs-lookup"><span data-stu-id="885bf-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="885bf-109">A tale scopo, è necessario essere connessi come membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="885bf-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="885bf-110">Per richiedere un certificato a un'Autorità di certificazione (CA) pubblica, non è necessario appartenere ad altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="885bf-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="885bf-111">Per richiedere un certificato dall'infrastruttura a chiave pubblica (PKI) dell'organizzazione, è necessario confermare le altre appartenenze ai gruppi di cui si ha bisogno.</span><span class="sxs-lookup"><span data-stu-id="885bf-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="885bf-112">Durante l'attività di richiesta, è possibile immettere credenziali alternative che verranno usate per richiedere il certificato dalla CA emittente della PKI.</span><span class="sxs-lookup"><span data-stu-id="885bf-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="885bf-113">Per richiedere un nuovo certificato, fare clic su **Richiedi**.</span><span class="sxs-lookup"><span data-stu-id="885bf-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="885bf-114">Per assegnare un certificato non ancora assegnato, fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="885bf-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="885bf-115">Per rimuovere un certificato precedentemente assegnato, fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="885bf-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="885bf-p103">Il pulsante **Rimuovi** sarà disponibile solo se in precedenza è stato assegnato un certificato. Se il pulsante **Rimuovi** risulta non disponibile (in grigio), non vi sono certificati assegnati.</span><span class="sxs-lookup"><span data-stu-id="885bf-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="885bf-118">Per visualizzare un certificato assegnato, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="885bf-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="885bf-p104">Il pulsante **Visualizza** sarà disponibile solo se in precedenza è stato assegnato un certificato. Se il pulsante **Visualizza** risulta non disponibile (in grigio), non vi sono certificati assegnati.</span><span class="sxs-lookup"><span data-stu-id="885bf-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="885bf-121">Per aggiornare la schermata con le assegnazioni correnti dei certificati, fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="885bf-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="885bf-122">Per importare un certificato non presente nell'archivio certificati, fare clic su **Importa certificato**.</span><span class="sxs-lookup"><span data-stu-id="885bf-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="885bf-123">**Importa certificato** in genere viene utilizzato per elaborare un certificato ricevuto mediante un processo diverso da una richiesta della Configurazione guidata certificati.</span><span class="sxs-lookup"><span data-stu-id="885bf-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="885bf-124">Si supponga ad esempio che l'amministratore dell'infrastruttura a chiave pubblica (PKI) crei un certificato e lo renda disponibile.</span><span class="sxs-lookup"><span data-stu-id="885bf-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="885bf-125">Usare il **certificato di importazione** per importare il certificato nell'archivio certificati del computer e renderlo disponibile per l'assegnazione a Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="885bf-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="885bf-p106">Per completare il processo di richiesta di un certificato a una CA della propria organizzazione per cui è necessaria l'approvazione dell'amministratore CA, fare clic su **Elabora certificati in sospeso**. Per la richiesta del certificato verrà restituito lo stato In sospeso e verrà visualizzato il numero di identificazione. Per proseguire con l'elaborazione di un certificato con stato In sospeso, fare clic su **Aggiorna** per abilitare il pulsante **Elabora certificati in sospeso**. Tale pulsante \*\*\*\* non sarà più visualizzato in grigio. È quindi possibile tentare di recuperare la richiesta in sospeso, ma lo stato resterà invariato finché il certificato non verrà emesso o rifiutato dall'amministratore CA. Il pulsante non sarà disponibile se non vi sono richieste in sospeso valide, create dalla Configurazione guidata certificati.</span><span class="sxs-lookup"><span data-stu-id="885bf-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

