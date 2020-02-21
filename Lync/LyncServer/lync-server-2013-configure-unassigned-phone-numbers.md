---
title: 'Lync Server 2013: configurare i numeri di telefono non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc319539c9dfe3de79f9cce62391ecd2886e8a1c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="68f6f-102">Configurare i numeri di telefono non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68f6f-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68f6f-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="68f6f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="68f6f-104">Lync Server consente di configurare cosa accade alle chiamate in arrivo ai numeri di telefono validi per l'organizzazione, ma non vengono assegnati a un utente o a un telefono.</span><span class="sxs-lookup"><span data-stu-id="68f6f-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="68f6f-105">Per configurare la gestione di tali chiamate, è possibile impostare una tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="68f6f-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="68f6f-106">È possibile utilizzare la tabella per instradare le chiamate a un'applicazione annuncio o a un server Messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="68f6f-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="68f6f-p102">La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene chiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se nella tabella si inseriscono interni non assegnati, è possibile personalizzare l'azione da eseguire per numeri specifici. Se ad esempio si modifica l'interno del servizio di assistenza clienti, è possibile inserire il vecchio numero nella tabella e assegnarlo a un annuncio in cui viene indicato il nuovo numero.</span><span class="sxs-lookup"><span data-stu-id="68f6f-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68f6f-113">Prima di configurare la tabella dei numeri non assegnati, è necessario che siano già stati definiti uno o più annunci oppure che sia stato configurato un operatore automatico di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="68f6f-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="68f6f-114">Per informazioni dettagliate sulla creazione di annunci, vedere <A href="lync-server-2013-create-an-announcement.md">creare un annuncio in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="68f6f-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="68f6f-115">Per sapere se sono state configurate le impostazioni di messaggistica unificata di Exchange, eseguire il cmdlet <STRONG>Get-CsExUmContact</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="68f6f-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="68f6f-116">Per informazioni dettagliate, <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span><span class="sxs-lookup"><span data-stu-id="68f6f-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="68f6f-117">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="68f6f-117">In This Section</span></span>

  - [<span data-ttu-id="68f6f-118">Creare o modificare un intervallo di numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68f6f-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="68f6f-119">Eliminare un intervallo di numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68f6f-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

