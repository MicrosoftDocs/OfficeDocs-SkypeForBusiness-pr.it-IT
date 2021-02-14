---
title: Response Group crearne uno nuovo o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: I gruppi di agenti definiscono quali utenti possono rispondere alle chiamate a un Response Group (anche definito agenti) e le impostazioni che si applicano a tutti gli agenti del gruppo.
ms.openlocfilehash: d38886289bdadc1f82bd87f93a8a108641fa1128
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808276"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="0a6e6-103">Response Group: creare un nuovo gruppo di agenti o modificarne uno esistente</span><span class="sxs-lookup"><span data-stu-id="0a6e6-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="0a6e6-104">I gruppi di agenti definiscono quali utenti possono rispondere alle chiamate a un Response Group (anche definito agenti) e le impostazioni che si applicano a tutti gli agenti del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0a6e6-105">Riferimento all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="0a6e6-105">UI Reference</span></span>

<span data-ttu-id="0a6e6-106">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="0a6e6-107">**Name** Ogni gruppo di agenti richiede un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="0a6e6-108">Usa un nome descrittivo che identifichi la funzione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="0a6e6-109">Ad esempio, Help Desk.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-109">For example, Help Desk.</span></span>

- <span data-ttu-id="0a6e6-110">**Descrizione** Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-110">**Description** This field is optional.</span></span> <span data-ttu-id="0a6e6-111">Usarlo per fornire maggiori dettagli sul gruppo.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="0a6e6-112">**Criteri di partecipazione** Specificare la modalità di accesso degli agenti al Response Group:</span><span class="sxs-lookup"><span data-stu-id="0a6e6-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="0a6e6-113">Selezionare **Informale** per specificare che gli agenti nel gruppo non devono accedere e disconnettersi. Gli agenti informali vengono connessi automaticamente all'accesso.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-113">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in.</span></span> <span data-ttu-id="0a6e6-114">L'impostazione predefinita è **Informale**.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-114">The default is **Informal**.</span></span>

  - <span data-ttu-id="0a6e6-115">Selezionare **Formale** per specificare che gli agenti nel gruppo devono accedere e disconnettersi. Quando si seleziona questa opzione, gli agenti selezionano una voce di menu nel client per aprire un browser e visualizzare una console della pagina Web per l'accesso e la disconnessione.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="0a6e6-116">**Tempo avviso (secondi)** Specificare il numero di secondi di squillo di un agente prima di offrire la chiamata al successivo agente disponibile.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="0a6e6-117">Il valore deve essere compreso tra 10 e 180 secondi.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="0a6e6-118">Il valore predefinito è 20 secondi.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="0a6e6-119">**Metodo di routing** Selezionare il metodo per determinare l'ordine in cui gli agenti ricevono le chiamate:</span><span class="sxs-lookup"><span data-stu-id="0a6e6-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="0a6e6-120">Selezionare **Inattività più lunga** per inoltrare una nuova chiamata prima all'agente che è stato inattivo (ha avuto una presenza **Disponibile** o **Inattivo**) più a lungo.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="0a6e6-p105">Per inoltrare una nuova chiamata a tutti gli agenti disponibili contemporaneamente, selezionare **Parallelo**. La chiamata verrà inviata al primo agente che la accetta.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="0a6e6-123">Per inoltrare una nuova chiamata a ogni agente a turno, selezionare **Round robin**.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="0a6e6-124">Per inoltrare sempre una nuova chiamata agli agenti in base all'ordine con cui sono elencati nell'elenco **Agente**, selezionare **Seriale**.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="0a6e6-125">Selezionare **Operatore** per offrire una nuova chiamata a tutti gli agenti che hanno eseguito l'accesso e all'applicazione Response Group contemporaneamente, indipendentemente dalla presenza corrente.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="0a6e6-126">Gli operatori e gli utenti client configurati come agenti possono visualizzare tutte le chiamate in attesa e rispondere alle chiamate in attesa in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="0a6e6-127">La chiamata viene inviata al primo agente che la accetta e gli altri operatori e utenti non la vedono più.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="0a6e6-128">**Agenti** Selezionare gli utenti che devono essere agenti per il Response Group in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6e6-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="0a6e6-129">Selezionare **Usa una lista di distribuzione di posta elettronica esistente** per utilizzare una lista di distribuzione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="0a6e6-130">Immettere l'indirizzo di posta elettronica della lista di distribuzione in **Indirizzo lista di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a6e6-p108">È possibile selezionare solo una lista di distribuzione per ogni gruppo di agenti e, se tale lista include liste di distribuzione nidificate, queste ultime non verranno incluse nel gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a6e6-133">L'ordine in cui sono elencati gli agenti nella lista di distribuzione determina l'ordine in cui riceveranno le chiamate per il routing di tipo round robin e seriale.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a6e6-134">Le appartenenze nascoste o gli elenchi nascosti potrebbero diventare visibili agli amministratori o agli utenti di Response Group.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="0a6e6-135">Per informazioni dettagliate, [vedere Creare o modificare un gruppo di agenti in Skype for Business.](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)</span><span class="sxs-lookup"><span data-stu-id="0a6e6-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="0a6e6-p110">Selezionare **Definisci un gruppo di agenti personalizzato** per selezionare gli utenti da assegnare come agenti per il Response Group. Fare clic su **Seleziona** per aggiungere un agente all'elenco oppure su **Rimuovi** per eliminare un agente selezionato dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="0a6e6-p111">Le frecce su e giù consentono di spostare un agente selezionato verso l'alto e verso il basso nell'elenco di agenti. L'ordine degli agenti nell'elenco determina l'ordine in cui ricevono le chiamate per il routing di tipo round robin e seriale.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="0a6e6-141">Per informazioni dettagliate sulle funzionalità e sulle funzionalità di Response Group, vedere [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="0a6e6-142">Per informazioni dettagliate sull'uso dei gruppi di agenti, vedere [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="0a6e6-142">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


