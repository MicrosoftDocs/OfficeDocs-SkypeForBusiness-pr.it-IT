---
title: 'Lync Server 2013: configurazione di Windows 8 per smart card virtuali'
description: 'Lync Server 2013: configurazione di Windows 8 per smart card virtuali.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112047f91a20dd552c628fb33eba7bb9ad3d0f01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542162"
---
# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="e610c-103">Configurazione di Windows 8 per l'utilizzo di smart card virtuali con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e610c-103">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e610c-104">_**Ultimo argomento modificato:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="e610c-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="e610c-105">Uno dei fattori da considerare quando si distribuisce l'autenticazione a due fattori e la tecnologia Smart Card è il costo dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="e610c-105">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="e610c-106">Windows 8 fornisce una serie di nuove funzionalità di sicurezza e una delle nuove funzionalità più interessanti è il supporto per le smart card virtuali.</span><span class="sxs-lookup"><span data-stu-id="e610c-106">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="e610c-107">Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1,2, le organizzazioni possono ora ottenere i vantaggi dell'accesso tramite smart card senza effettuare ulteriori investimenti nell'hardware.</span><span class="sxs-lookup"><span data-stu-id="e610c-107">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="e610c-108">Per ulteriori informazioni, vedere Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365) .</span><span class="sxs-lookup"><span data-stu-id="e610c-108">For more information, see Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="e610c-109">Per configurare Windows 8 per smart card virtuali</span><span class="sxs-lookup"><span data-stu-id="e610c-109">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="e610c-110">Eseguire l'accesso al computer con Windows 8 utilizzando le credenziali di un utente abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="e610c-110">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="e610c-111">Nella schermata Start di Windows 8, spostare il cursore nell'angolo in basso a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="e610c-111">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="e610c-112">Selezionare l'opzione di **ricerca** e quindi cercare il **prompt dei comandi**.</span><span class="sxs-lookup"><span data-stu-id="e610c-112">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="e610c-113">Fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="e610c-113">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="e610c-114">Aprire la console di gestione TPM (Trusted Platform Module) eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e610c-114">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="e610c-115">Dalla console di gestione TPM, verificare che la versione specifica TPM sia almeno 1,2</span><span class="sxs-lookup"><span data-stu-id="e610c-115">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e610c-116">Se viene visualizzata una finestra di dialogo in cui viene indicato che non è possibile trovare un modulo TPM (Trusted Trust Platform Module), verificare che il computer disponga di un modulo TPM compatibile e che sia abilitato nel BIOS del sistema.</span><span class="sxs-lookup"><span data-stu-id="e610c-116">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="e610c-117">Chiudere la console di gestione TPM</span><span class="sxs-lookup"><span data-stu-id="e610c-117">Close the TPM management console</span></span>

8.  <span data-ttu-id="e610c-118">Al prompt dei comandi creare una nuova smart card virtuale utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e610c-118">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e610c-119">Per fornire un valore PIN personalizzato quando si crea la smart card virtuale, utilizzare invece il prompt di/pin.</span><span class="sxs-lookup"><span data-stu-id="e610c-119">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="e610c-120">Al prompt dei comandi, aprire la console di gestione computer eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e610c-120">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="e610c-121">Nella console Gestione computer selezionare **Gestione dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="e610c-121">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="e610c-122">Espandere **lettori di smart card**.</span><span class="sxs-lookup"><span data-stu-id="e610c-122">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="e610c-123">Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e610c-123">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

