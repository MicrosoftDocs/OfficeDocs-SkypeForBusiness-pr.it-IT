---
title: Configurare l'archivio contatti personali nei computer client Lync 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: "Riepilogo: configurare l'archivio contatti personale utilizzato dai client legacy."
ms.openlocfilehash: 5f2131fd1e960e658d4257f0c86dd61a241aa499
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109672"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="60888-103">Configurare l'archivio contatti personali nei computer client Lync 2010</span><span class="sxs-lookup"><span data-stu-id="60888-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="60888-104">Se stai integrando Skype for Business Server 2015 e Exchange Server 2016 o Exchange Server 2013, devi configurare l'archivio contatti personale utilizzato dai client.</span><span class="sxs-lookup"><span data-stu-id="60888-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="60888-105">In particolare, è consigliabile configurare Skype for Business per l'utilizzo di Exchange come archivio contatti personale e, allo stesso tempo, assicurarsi che gli utenti non siano in grado di ignorare tale decisione.</span><span class="sxs-lookup"><span data-stu-id="60888-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="60888-106">A tale scopo, è possibile creare e configurare un valore del Registro di sistema in ogni computer client.</span><span class="sxs-lookup"><span data-stu-id="60888-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60888-107">La procedura seguente è necessaria solo per i client che utilizzano il client Lync 2010 o versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="60888-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="60888-108">Il client Lync 2013 e tutti i client Skype for Business non avranno la possibilità di ignorare le impostazioni dell'archivio contatti.</span><span class="sxs-lookup"><span data-stu-id="60888-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="60888-109">Per configurare questo valore in un singolo computer, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="60888-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="60888-110">Nel computer client fare clic sul pulsante **Start** e quindi scegliere **Esegui.**</span><span class="sxs-lookup"><span data-stu-id="60888-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="60888-111">Nella finestra di dialogo **Esegui** digitare regedit e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="60888-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="60888-112">Nell'Editor del Registro di **sistema espandere HKEY_LOCAL_MACHINE**, **software**, **Criteri**, **Microsoft** e quindi espandere **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="60888-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="60888-113">Fare clic con **il Communicator,** scegliere **Nuovo** e quindi **valore DWORD (32 bit).**</span><span class="sxs-lookup"><span data-stu-id="60888-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="60888-114">Dopo aver creato il nuovo valore, digitare PersonalContactStoreOverride e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="60888-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="60888-115">Verificare che il valore di PersonalContactStoreOverride sia impostato su 0 e quindi chiudere l'editor del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="60888-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="60888-116">Se si desidera eseguire le stesse modifiche in più computer è possibile creare un oggetto Criteri di gruppo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="60888-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="60888-117">Per informazioni dettagliate su come eseguire questa operazione in Windows 10, vedi l'articolo [Creare un oggetto Criteri di](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) gruppo.</span><span class="sxs-lookup"><span data-stu-id="60888-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
