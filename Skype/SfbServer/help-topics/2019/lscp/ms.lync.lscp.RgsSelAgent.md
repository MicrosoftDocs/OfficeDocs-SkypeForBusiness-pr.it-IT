---
title: Selezionare agenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: Gli agenti sono utenti designati per rispondere alle chiamate di Response Group. Ai Response Group deve essere assegnato un gruppo di agenti che identifichi quali agenti possono ricevere le chiamate da tale gruppo. Un modo per creare un gruppo di agenti consiste nel definire un gruppo personalizzato selezionando gli utenti idonei. Gli utenti idonei sono abilitati per Skype for Business Server e Enterprise Voice.
ms.openlocfilehash: 0efc0c0afeff33472075c68cf4300bb5ecf51c66
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793474"
---
# <a name="select-agents"></a><span data-ttu-id="1c161-106">Selezionare agenti</span><span class="sxs-lookup"><span data-stu-id="1c161-106">Select Agents</span></span>

<span data-ttu-id="1c161-107">Gli agenti sono utenti designati per rispondere alle chiamate di Response Group.</span><span class="sxs-lookup"><span data-stu-id="1c161-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="1c161-108">Ai Response Group deve essere assegnato un gruppo di agenti che identifichi quali agenti possono ricevere le chiamate da tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="1c161-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="1c161-109">Un modo per creare un gruppo di agenti consiste nel definire un gruppo personalizzato selezionando gli utenti idonei.</span><span class="sxs-lookup"><span data-stu-id="1c161-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="1c161-110">Gli utenti idonei sono abilitati per Skype for Business Server e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1c161-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="1c161-111">È possibile usare la finestra di dialogo **Seleziona agenti** per selezionare gli utenti da aggiungere a un gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="1c161-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1c161-112">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="1c161-112">UI Reference</span></span>

<span data-ttu-id="1c161-113">Nell'elenco seguente sono descritti i controlli presenti nella finestra di dialogo **Seleziona agenti**.</span><span class="sxs-lookup"><span data-stu-id="1c161-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="1c161-114">**Trovare** Cerca l'indirizzo SIP o il nome visualizzato per un utente.</span><span class="sxs-lookup"><span data-stu-id="1c161-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="1c161-115">Immettere il nome o l'indirizzo per intero o in parte.</span><span class="sxs-lookup"><span data-stu-id="1c161-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="1c161-116">Lascia vuota la casella di ricerca per visualizzare tutti gli utenti abilitati per Skype for Business Server e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1c161-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="1c161-117">**Numero massimo di utenti da visualizzare** Modifica il numero di risultati restituiti visualizzati.</span><span class="sxs-lookup"><span data-stu-id="1c161-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="1c161-118">Usare questo contatore per limitare la ricerca se si prevede di ottenere molti risultati.</span><span class="sxs-lookup"><span data-stu-id="1c161-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="1c161-119">Nell'elenco seguente sono descritti i campi presenti nella finestra di dialogo **Seleziona agenti**.</span><span class="sxs-lookup"><span data-stu-id="1c161-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="1c161-120">**Agente** Visualizza i nomi utente restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="1c161-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="1c161-121">**Indirizzo SIP** Visualizza gli indirizzi SIP degli utenti restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="1c161-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="1c161-122">**Telefonia** Visualizza il valore del campo **telefonia** definito per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1c161-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="1c161-123">**Abilitato** Visualizza il valore del campo **Enabled per Lync Server** definito per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1c161-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="1c161-124">Per informazioni dettagliate sull'uso dei gruppi di agenti, vedere [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="1c161-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


