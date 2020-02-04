---
title: 'Lync Server 2013: Configurare la tabella dei numeri non assegnati'
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
ms.openlocfilehash: b99679d439257b54b6bb40d8e724bb63da4a1ea5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="3d181-102">Configurare la tabella dei numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d181-102">Configure the unassigned number table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d181-103">_**Argomento Ultima modifica:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3d181-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3d181-104">In Lync Server 2013 è possibile specificare cosa accade alle chiamate in arrivo per i numeri di telefono validi per l'organizzazione, ma non sono assegnati a un utente o un telefono.</span><span class="sxs-lookup"><span data-stu-id="3d181-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="3d181-105">I chiamanti possono ascoltare un messaggio o possono essere instradati a un'altra destinazione o entrambi.</span><span class="sxs-lookup"><span data-stu-id="3d181-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="3d181-106">La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa.</span><span class="sxs-lookup"><span data-stu-id="3d181-106">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="3d181-107">È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi.</span><span class="sxs-lookup"><span data-stu-id="3d181-107">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="3d181-108">La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene chiamata solo se un chiamante compone un numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="3d181-108">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="3d181-109">Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella.</span><span class="sxs-lookup"><span data-stu-id="3d181-109">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="3d181-110">Se si includono estensioni non assegnate nella tabella, è possibile modificare l'azione che si verifica per i numeri specifici.</span><span class="sxs-lookup"><span data-stu-id="3d181-110">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="3d181-111">Ad esempio, se si modifica l'estensione per il servizio di assistenza clienti, è possibile includere il vecchio numero di servizio clienti nella tabella e quindi assegnarlo a un annuncio che fornisce il nuovo numero.</span><span class="sxs-lookup"><span data-stu-id="3d181-111">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3d181-112">Prima di configurare la tabella dei numeri non assegnati, è necessario che il sistema disponga già di annunci definiti o di un operatore automatico di messaggistica UNIFICAta di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3d181-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="3d181-113">Quando qualcuno chiama un numero non assegnato, Lync Server cerca nella tabella numeri non assegnati dall'alto verso il basso e usa il primo intervallo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3d181-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="3d181-114">Deve quindi essere specificata un'azione che si vuole eseguire come ultima risorsa per l'ultimo intervallo della tabella.</span><span class="sxs-lookup"><span data-stu-id="3d181-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3d181-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3d181-115">In This Section</span></span>

<span data-ttu-id="3d181-116">[Creare o modificare un intervallo di numeri non assegnati in Lync server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [creare un annuncio in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="3d181-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

