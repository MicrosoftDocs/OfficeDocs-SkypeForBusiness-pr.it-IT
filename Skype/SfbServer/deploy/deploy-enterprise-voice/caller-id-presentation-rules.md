---
title: Creare o modificare una regola di traduzione per la presentazione dell'ID chiamante in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: "Riepilogo: informazioni su come configurare l'ID chiamante tramite il pannello di controllo di Skype for Business Server."
ms.openlocfilehash: d6b2e594d0f16e9b3278145087af854650a957da
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768159"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="6b0aa-103">Creare o modificare una regola di traduzione per la presentazione dell'ID chiamante in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6b0aa-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="6b0aa-104">**Riepilogo:** Informazioni su come configurare l'ID chiamante tramite il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="6b0aa-105">Con Skype for Business Server, il numero di telefono della festa chiamata (ovvero il numero di telefono chiamato) può essere tradotto dal formato E. 164 al formato di chiamata locale richiesto dal _peer trunk_ , ovvero il gateway associato, il PBX (Private Branch Exchange) o il trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="6b0aa-106">A tale scopo, è necessario definire una o più regole di traduzione per tradurre l'URI della richiesta prima di instradarlo al peer trunk.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="6b0aa-107">Skype for Business Server offre anche l'opzione di tradurre anche il numero di telefono della parte chiamante (ovvero il numero di telefono da cui il chiamante chiama) dal formato E. 164 al formato di chiamata locale richiesto dal peer trunk.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="6b0aa-108">Ad esempio, è possibile scrivere una regola di traduzione per rimuovere + 44 dall'inizio di una stringa di chiamata e sostituirla con 0144.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6b0aa-109">Per configurare l'ID chiamante tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6b0aa-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6b0aa-110">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="6b0aa-111">Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="6b0aa-112">Nella pagina **trunk Configuration** fare doppio clic su un trunk esistente, ad esempio il trunk **globale** , per visualizzare la finestra di dialogo **modifica configurazione trunk** .</span><span class="sxs-lookup"><span data-stu-id="6b0aa-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="6b0aa-113">Per configurare la presentazione dell'ID chiamante:</span><span class="sxs-lookup"><span data-stu-id="6b0aa-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="6b0aa-114">Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="6b0aa-115">In **regole di traduzione dei numeri di chiamata**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="6b0aa-116">Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="6b0aa-117">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di traduzione](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-117">For details about defining a new rule, see  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="6b0aa-118">Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="6b0aa-119">Per informazioni dettagliate, vedere [definizione delle regole di traduzione](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-119">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="6b0aa-120">Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="6b0aa-121">Per informazioni dettagliate, vedere [definizione delle regole di traduzione](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span><span class="sxs-lookup"><span data-stu-id="6b0aa-121">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span>

   - <span data-ttu-id="6b0aa-122">Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="6b0aa-123">Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="6b0aa-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>


