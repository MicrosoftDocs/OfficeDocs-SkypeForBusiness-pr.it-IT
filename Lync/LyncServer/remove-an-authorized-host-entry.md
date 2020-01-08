---
title: Rimuovere una voce dell'host autorizzato
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca9bc99382e904c398dbb7434b2ee6343ab661ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="7f7c9-102">Rimuovere una voce dell'host autorizzato</span><span class="sxs-lookup"><span data-stu-id="7f7c9-102">Remove an authorized host entry</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f7c9-103">_**Argomento Ultima modifica:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="7f7c9-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="7f7c9-104">Questo argomento descrive come rimuovere una voce dell'host autorizzato legacy (nota come *voce di applicazione attendibile* in Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="7f7c9-104">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="7f7c9-105">Quando si esegue la migrazione del controllo delle chiamate remote a una distribuzione di Lync Server 2013, è necessario rimuovere le voci di host autorizzati esistenti per tutti i gateway SIP/CSTA nella distribuzione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7f7c9-105">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="7f7c9-106">È necessario usare gli strumenti di amministrazione inclusi in Office Communications Server 2007 R2 per rimuovere le voci esistenti dell'host autorizzato.</span><span class="sxs-lookup"><span data-stu-id="7f7c9-106">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="7f7c9-107">Per rimuovere una voce ospitante autorizzata in una distribuzione di Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7f7c9-107">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="7f7c9-108">Aprire la console di amministrazione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7f7c9-108">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="7f7c9-109">Espandere l'albero e fare clic con il pulsante destro del mouse sul pool in cui è stato creato l'host autorizzato.</span><span class="sxs-lookup"><span data-stu-id="7f7c9-109">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="7f7c9-110">Fare clic su **Proprietà**e quindi su **Proprietà front-end**.</span><span class="sxs-lookup"><span data-stu-id="7f7c9-110">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="7f7c9-111">Fare clic sulla scheda **autorizzazione host** .</span><span class="sxs-lookup"><span data-stu-id="7f7c9-111">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="7f7c9-112">Selezionare un server e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="7f7c9-112">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="7f7c9-113">In **Proprietà**fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f7c9-113">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

