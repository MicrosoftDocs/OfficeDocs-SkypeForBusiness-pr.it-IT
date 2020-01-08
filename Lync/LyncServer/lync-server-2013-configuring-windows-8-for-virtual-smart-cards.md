---
title: 'Lync Server 2013: configurazione di Windows 8 per smart card virtuali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="e7075-102">Configurazione di Windows 8 per l'uso di smart card virtuali con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7075-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7075-103">_**Argomento Ultima modifica:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="e7075-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="e7075-104">Un fattore da tenere in considerazione quando si distribuisce l'autenticazione a due fattori e la tecnologia Smart Card è il costo di implementazione.</span><span class="sxs-lookup"><span data-stu-id="e7075-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="e7075-105">Windows 8 offre una serie di nuove funzionalità di sicurezza e una delle nuove caratteristiche più interessanti è il supporto per le smart card virtuali.</span><span class="sxs-lookup"><span data-stu-id="e7075-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="e7075-106">Per i computer dotati di un chip TPM (Trusted Platform Module) che soddisfa la specifica versione 1,2, le organizzazioni possono ora ottenere i vantaggi dell'accesso tramite smart card senza apportare ulteriori investimenti nell'hardware.</span><span class="sxs-lookup"><span data-stu-id="e7075-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="e7075-107">Per altre informazioni, vedere uso di smart card virtuali con Windows 8 [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)at.</span><span class="sxs-lookup"><span data-stu-id="e7075-107">For more information, see Using Virtual Smart Cards with Windows 8 at [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="e7075-108">Per configurare Windows 8 per smart card virtuali</span><span class="sxs-lookup"><span data-stu-id="e7075-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="e7075-109">Accedere al computer con Windows 8 usando le credenziali di un utente abilitato per Lync.</span><span class="sxs-lookup"><span data-stu-id="e7075-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="e7075-110">Nella schermata Start di Windows 8 Posizionare il cursore nell'angolo in basso a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="e7075-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="e7075-111">Selezionare l'opzione di **ricerca** e quindi cercare **prompt dei comandi**.</span><span class="sxs-lookup"><span data-stu-id="e7075-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="e7075-112">Fare clic con il pulsante destro del mouse sul **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="e7075-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="e7075-113">Aprire la console di gestione TPM (Trusted Platform Module) eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e7075-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="e7075-114">Nella console di gestione TPM verificare che la versione specifica del TPM sia di almeno 1,2</span><span class="sxs-lookup"><span data-stu-id="e7075-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7075-115">Se viene visualizzata una finestra di dialogo che indica che non è possibile trovare un modulo TPM (compatible Trust Platform Module), verificare che il computer disponga di un modulo TPM compatibile e che sia abilitato nel BIOS di sistema.</span><span class="sxs-lookup"><span data-stu-id="e7075-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="e7075-116">Chiudere la console di gestione TPM</span><span class="sxs-lookup"><span data-stu-id="e7075-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="e7075-117">Dal prompt dei comandi creare una nuova smart card virtuale usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e7075-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7075-118">Per specificare un valore PIN personalizzato durante la creazione della smart card virtuale, usare invece il prompt di/pin.</span><span class="sxs-lookup"><span data-stu-id="e7075-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="e7075-119">Dal prompt dei comandi aprire la console di gestione computer eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e7075-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="e7075-120">Nella console di gestione computer selezionare **Gestione dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="e7075-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="e7075-121">Espandi **lettori di smart card**.</span><span class="sxs-lookup"><span data-stu-id="e7075-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="e7075-122">Verificare che il nuovo lettore di smart card virtuale sia stato creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e7075-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

