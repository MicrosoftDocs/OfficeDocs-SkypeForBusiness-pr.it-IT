---
title: Selezionare agenti
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: Gli agenti sono utenti designati per rispondere alle chiamate di Response Group. Ai Response Group deve essere assegnato un gruppo di agenti che identifichi quali agenti possono ricevere le chiamate da tale gruppo. Un modo per creare un gruppo di agenti consiste nel definire un gruppo personalizzato selezionando gli utenti idonei. Gli utenti idonei sono abilitati per Skype for Business Server e VoIP aziendale.
ms.openlocfilehash: 3c79d46096a39cde01ea4c3246f71b972933c4d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829146"
---
# <a name="select-agents"></a><span data-ttu-id="d2347-106">Selezionare agenti</span><span class="sxs-lookup"><span data-stu-id="d2347-106">Select Agents</span></span>

<span data-ttu-id="d2347-107">Gli agenti sono utenti designati per rispondere alle chiamate di Response Group.</span><span class="sxs-lookup"><span data-stu-id="d2347-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="d2347-108">Ai Response Group deve essere assegnato un gruppo di agenti che identifichi quali agenti possono ricevere le chiamate da tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="d2347-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="d2347-109">Un modo per creare un gruppo di agenti consiste nel definire un gruppo personalizzato selezionando gli utenti idonei.</span><span class="sxs-lookup"><span data-stu-id="d2347-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="d2347-110">Gli utenti idonei sono abilitati per Skype for Business Server e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d2347-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="d2347-111">È possibile usare la finestra di dialogo **Seleziona agenti** per selezionare gli utenti da aggiungere a un gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="d2347-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d2347-112">Riferimento all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d2347-112">UI Reference</span></span>

<span data-ttu-id="d2347-113">Nell'elenco seguente sono descritti i controlli presenti nella finestra di dialogo **Seleziona agenti**.</span><span class="sxs-lookup"><span data-stu-id="d2347-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="d2347-114">**Individuare** Cerca l'indirizzo SIP o il nome visualizzato di un utente.</span><span class="sxs-lookup"><span data-stu-id="d2347-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="d2347-115">Immettere il nome o l'indirizzo per intero o in parte.</span><span class="sxs-lookup"><span data-stu-id="d2347-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="d2347-116">Lasciare vuota la casella di ricerca per visualizzare tutti gli utenti abilitati per Skype for Business Server e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d2347-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="d2347-117">**Numero massimo di utenti da visualizzare** Modifica il numero di risultati restituiti visualizzati.</span><span class="sxs-lookup"><span data-stu-id="d2347-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="d2347-118">Usare questo contatore per limitare la ricerca se si prevede di ottenere molti risultati.</span><span class="sxs-lookup"><span data-stu-id="d2347-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="d2347-119">Nell'elenco seguente sono descritti i campi presenti nella finestra di dialogo **Seleziona agenti**.</span><span class="sxs-lookup"><span data-stu-id="d2347-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="d2347-120">**Agente** Visualizza i nomi utente restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="d2347-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="d2347-121">**Indirizzo SIP** Visualizza gli indirizzi SIP dell'utente restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="d2347-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="d2347-122">**Telefonia** Visualizza il valore del campo **telefonia** definito per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d2347-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="d2347-123">**Attivata** Visualizza il valore del campo **abilitato per Lync Server** definito per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d2347-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="d2347-124">Per informazioni dettagliate sull'uso dei gruppi di agenti, vedere [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="d2347-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


