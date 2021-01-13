---
title: Servizio impostazioni utente per il dashboard qualità chiamata (CQD)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: "Riepilogo: informazioni sul servizio impostazioni utente, che fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803037"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="8d280-104">Servizio impostazioni utente per il dashboard qualità chiamata (CQD)</span><span class="sxs-lookup"><span data-stu-id="8d280-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="8d280-105">**Riepilogo:** Informazioni sul servizio impostazioni utente, che fa parte dell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="8d280-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="8d280-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8d280-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8d280-107">Il servizio impostazioni utente fa parte dell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="8d280-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="8d280-108">Servizio impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="8d280-108">User Settings Service</span></span>

<span data-ttu-id="8d280-109">Le impostazioni utente sono coppie chiave-valore che le applicazioni possono utilizzare per archiviare i metadati per diversi scopi, inclusa la personalizzazione dei comportamenti dell'applicazione per utente.</span><span class="sxs-lookup"><span data-stu-id="8d280-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="8d280-110">Ogni utente riceve un archivio per le impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="8d280-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="8d280-111">Solo i proprietari possono aggiungere, modificare e rimuovere le impostazioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8d280-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="8d280-112">**Impostazioni globali**</span><span class="sxs-lookup"><span data-stu-id="8d280-112">**Global Settings**</span></span>
  
<span data-ttu-id="8d280-113">Le impostazioni globali sono le impostazioni utente di proprietà dell'utente del sistema e tutti gli utenti dispongono dell'accesso in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="8d280-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="8d280-114">Le impostazioni globali sono costanti: vengono create durante la creazione del repository e non cambiano mai.</span><span class="sxs-lookup"><span data-stu-id="8d280-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="8d280-115">Ogni utente può eseguire l'override delle impostazioni globali creando le impostazioni utente con le stesse chiavi.</span><span class="sxs-lookup"><span data-stu-id="8d280-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="8d280-116">Quando l'applicazione richiede le impostazioni utente effettive, l'API restituisce un insieme di impostazioni globali unite alle impostazioni utente, con ogni impostazione che sostituisce l'impostazione globale corrispondente se le chiavi sono uguali.</span><span class="sxs-lookup"><span data-stu-id="8d280-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="8d280-117">L'API può anche restituire solo le impostazioni utente in modo che le applicazioni possano scoprire quali impostazioni sono sottoposte a override.</span><span class="sxs-lookup"><span data-stu-id="8d280-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="8d280-118">Le operazioni REST sono incluse nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8d280-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="8d280-119">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="8d280-119">**Operation**</span></span>|<span data-ttu-id="8d280-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8d280-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8d280-121">Ottieni impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="8d280-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="8d280-122">Ottenere le impostazioni utente restituisce un elenco di impostazioni per un utente specificato.</span><span class="sxs-lookup"><span data-stu-id="8d280-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="8d280-123">Ottieni impostazione utente</span><span class="sxs-lookup"><span data-stu-id="8d280-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="8d280-124">Ottenere l'impostazione utente restituisce una singola impostazione utente.</span><span class="sxs-lookup"><span data-stu-id="8d280-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

