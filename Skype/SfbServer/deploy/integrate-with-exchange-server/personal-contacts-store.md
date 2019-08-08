---
title: Configurare l'archivio dei contatti personali nei computer client di Lync 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: "Riepilogo: configurare l'archivio contatti personale usato dai client legacy."
ms.openlocfilehash: 26352517ea31b5556784f6f1ea8d1ce661cfe184
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244193"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="0aaf7-103">Configurare l'archivio dei contatti personali nei computer client di Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0aaf7-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="0aaf7-104">Se si integrano Skype for Business Server 2015 ed Exchange Server 2016 o Exchange Server 2013, è necessario configurare l'archivio contatti personale usato dai client.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="0aaf7-105">In particolare, devi configurare Skype for business in modo da usare Exchange come archivio contatti personale e, allo stesso tempo, assicurarti che gli utenti non siano in grado di ignorare tale decisione.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="0aaf7-106">Questa operazione può essere eseguita creando e configurando un valore del registro di sistema in ogni computer client.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0aaf7-107">La procedura seguente è necessaria solo per i client che usano il client Lync 2010 o versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="0aaf7-108">Il client Lync 2013 e tutti i client Skype for business non avranno la possibilità di eseguire l'override delle impostazioni dell'archivio contatti.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="0aaf7-109">Per configurare questo valore in un singolo computer, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="0aaf7-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="0aaf7-110">Nel computer client fare clic su **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="0aaf7-111">Nella finestra di dialogo **Esegui** Digitare regedit e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="0aaf7-112">In Editor del registro di sistema, Espandi **HKEY_LOCAL_MACHINE**, Espandi **software**, Espandi **criteri**, Espandi **Microsoft**e quindi Espandi **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="0aaf7-113">Fare clic con il pulsante destro del mouse su **Communicator**, scegliere **nuovo**e quindi fare clic su **valore DWORD (32 bit)**.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="0aaf7-114">Dopo la creazione del nuovo valore, digitare PersonalContactStoreOverride e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="0aaf7-115">Verificare che il valore di PersonalContactStoreOverride sia impostato su 0 e quindi chiudere l'editor del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="0aaf7-116">Se è necessario apportare questa stessa modifica su più computer, è possibile creare un oggetto Criteri di gruppo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0aaf7-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="0aaf7-117">Per informazioni dettagliate su come eseguire questa operazione in Windows 10, vedere l'articolo [creare un oggetto Criteri di gruppo](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .</span><span class="sxs-lookup"><span data-stu-id="0aaf7-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
