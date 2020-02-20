---
title: Eseguire la migrazione dei numeri di accesso esterno
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fcc5b7dac5c9769d92afc86e7036f7e410f2278
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="9858d-102">Eseguire la migrazione dei numeri di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="9858d-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9858d-103">_**Ultimo argomento modificato:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="9858d-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="9858d-104">La migrazione dei numeri di accesso esterno richiede due passaggi: l'esecuzione del cmdlet **Import-CsLegacyConfiguration** (completata in precedenza in [criteri e impostazioni di importazione](import-policies-and-settings.md)) per eseguire la migrazione di dial plan e altre impostazioni dei numeri di accesso esterno e l'esecuzione del cmdlet **Move-CsApplicationEndpoint** per eseguire la migrazione degli oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="9858d-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="9858d-105">Per eseguire la migrazione dei numeri di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="9858d-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="9858d-106">Aprire lo strumento di amministrazione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9858d-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="9858d-107">Nell'albero della console fare clic con il pulsante destro del mouse sul nodo della foresta, scegliere **Proprietà** e quindi fare clic su **Operatore Conferenza**.</span><span class="sxs-lookup"><span data-stu-id="9858d-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="9858d-108">Nella scheda **Numeri di accesso** fare clic su **Servito dal pool** per ordinare i numeri telefonici di accesso in base al pool associato e identificare tutti i numeri di accesso per il pool da cui si sta eseguendo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="9858d-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="9858d-109">Per identificare l'URI SIP per ogni numero di accesso, fare doppio clic sul numero di accesso per aprire la finestra di dialogo **Modifica numero Operatore Conferenza**. L'URI è indicato in **URI SIP**.</span><span class="sxs-lookup"><span data-stu-id="9858d-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="9858d-110">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9858d-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="9858d-111">Per spostare ogni numero di accesso esterno in un pool ospitato in Lync Server 2013, eseguire:</span><span class="sxs-lookup"><span data-stu-id="9858d-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="9858d-112">Nello strumento di amministrazione di Office Communications Server 2007 R2, nella scheda **numeri di accesso** , verificare che non rimangano numeri di accesso esterno per il pool di Office communications Server 2007 R2 da cui si esegue la migrazione.</span><span class="sxs-lookup"><span data-stu-id="9858d-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

