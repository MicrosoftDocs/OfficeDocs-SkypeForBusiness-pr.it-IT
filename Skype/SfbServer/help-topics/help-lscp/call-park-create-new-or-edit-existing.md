---
title: Parcheggio di chiamata creare nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Gli intervalli di numeri di parcheggio per le chiamate definiscono i numeri temporanei in cui vengono mantenute le chiamate parcheggiate finché qualcuno non li recupera o ne esce fuori.
ms.openlocfilehash: 6b67200de60e9ed55969468351419c10ecabe5bc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686979"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="2e83a-103">Parcheggio di chiamata: creare un nuovo intervallo di codici orbit o modificarne uno esistente</span><span class="sxs-lookup"><span data-stu-id="2e83a-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="2e83a-104">Gli intervalli di numeri di parcheggio per le chiamate definiscono i numeri temporanei in cui vengono mantenute le chiamate parcheggiate finché qualcuno non li recupera o ne esce fuori.</span><span class="sxs-lookup"><span data-stu-id="2e83a-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2e83a-105">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="2e83a-105">UI Reference</span></span>

<span data-ttu-id="2e83a-106">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2e83a-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2e83a-107">**Nome** Digitare un nome descrittivo che identifichi l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="2e83a-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="2e83a-108">Questo nome non potrà essere modificato dopo aver salvato l'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="2e83a-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="2e83a-109">**Intervallo di numeri** Nel primo campo digitare il numero iniziale dell'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="2e83a-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="2e83a-110">Nel secondo campo digitare il numero finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="2e83a-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="2e83a-111">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</span><span class="sxs-lookup"><span data-stu-id="2e83a-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="2e83a-112">Il valore del numero iniziale dell'intervallo deve avere la stessa lunghezza del numero finale.</span><span class="sxs-lookup"><span data-stu-id="2e83a-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="2e83a-p103">L'intervallo di numeri deve essere univoco e non può sovrapporsi ad altri intervalli.</span><span class="sxs-lookup"><span data-stu-id="2e83a-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="2e83a-115">Se l'intervallo di numeri inizia con il \* carattere o #, l'intervallo deve essere maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="2e83a-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="2e83a-116">Valori validi: deve corrispondere alla stringa di espressione regolare (\\[\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="2e83a-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="2e83a-117">Questo significa che il valore deve essere una stringa che inizia con il \* carattere o # o un numero da 1 a 9 (il primo carattere non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="2e83a-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="2e83a-118">Se il primo carattere è \* o #, il carattere seguente deve essere un numero da 1 a 9 (non può essere uno zero).</span><span class="sxs-lookup"><span data-stu-id="2e83a-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="2e83a-119">I caratteri successivi possono essere qualsiasi numero da 0 a 9 fino a sette caratteri aggiuntivi (ad esempio, "#6000"\*, "92000"\*, "95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="2e83a-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="2e83a-120">Se il primo carattere non \* è o #, il primo carattere deve essere un numero da 1 a 9 (non può essere zero), seguito da un massimo di otto caratteri, ognuno dei quali è compreso tra 0 e 9 (ad esempio: 915551212; 41212; 300).</span><span class="sxs-lookup"><span data-stu-id="2e83a-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="2e83a-p105">Non è possibile definire più di 50.000 numeri in totale per ogni pool. Ogni intervallo di numeri include in genere 100 numeri o meno, ma può essere molto più esteso a condizione che includa meno di 10.000 numeri. Anziché specificare un numero iniziale "7000000" e un numero finale "8000000", ad esempio, valutare la possibilità di specificare un numero iniziale "7000000" e un numero finale "7000100".</span><span class="sxs-lookup"><span data-stu-id="2e83a-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="2e83a-124">**Nome di dominio completo del server di destinazione** Selezionare il nome di dominio completo (FQDN) o l'ID servizio del servizio applicazione che ospita l'applicazione Call Park.</span><span class="sxs-lookup"><span data-stu-id="2e83a-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="2e83a-125">Tutte le chiamate parcheggiate nei numeri entro l'intervallo specificato dal numero iniziale e da quello finale nell'intervallo saranno instradate a questo server o pool.</span><span class="sxs-lookup"><span data-stu-id="2e83a-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="2e83a-126">Per informazioni dettagliate sulle caratteristiche e le funzionalità di Call Park, vedere [pianificare il parcheggio delle chiamate in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="2e83a-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="2e83a-127">Per informazioni dettagliate sull'uso degli intervalli di numeri di Call Park, vedere [configurare le estensioni dei numeri di telefono per le chiamate di parcheggio](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="2e83a-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


