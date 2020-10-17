---
title: 'Lync Server 2013: configurare la tabella dei numeri non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c73027511ec8798010f1d22fb9bd19eeab27a7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520253"
---
# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="36210-102">Configurare la tabella dei numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36210-102">Configure the unassigned number table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36210-103">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="36210-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="36210-104">In Lync Server 2013, è possibile specificare cosa succede alle chiamate in arrivo per i numeri di telefono validi per l'organizzazione, ma non vengono assegnati a un utente o a un telefono.</span><span class="sxs-lookup"><span data-stu-id="36210-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="36210-105">I chiamanti possono ascoltare un messaggio, essere instradati verso un'altra destinazione oppure entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="36210-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="36210-p102">La configurazione della tabella dei numeri non assegnati dipende dal modo in cui si desidera utilizzarla. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene richiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se nella tabella si inseriscono interni non assegnati, è possibile modificare l'azione da eseguire per numeri specifici. Se ad esempio si modifica l'interno del servizio di assistenza clienti, è possibile inserire il vecchio numero nella tabella e quindi assegnarlo a un annuncio in cui viene indicato il nuovo numero.</span><span class="sxs-lookup"><span data-stu-id="36210-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="36210-112">Prima di configurare la tabella dei numeri non assegnati, è necessario che nel sistema siano già stati definiti annunci o che sia stato impostato un operatore automatico di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="36210-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="36210-113">Quando qualcuno chiama un numero non assegnato, Lync Server esegue la ricerca nella tabella dei numeri non assegnati dall'alto verso il basso e utilizza il primo intervallo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="36210-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="36210-114">Pertanto, per l'ultimo intervallo della tabella è consigliabile specificare un'azione che si desidera venga eseguita come ultima risorsa.</span><span class="sxs-lookup"><span data-stu-id="36210-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36210-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="36210-115">In This Section</span></span>

<span data-ttu-id="36210-116">[Creare o modificare un intervallo di numeri non assegnati in Lync server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [creare un annuncio in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="36210-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

