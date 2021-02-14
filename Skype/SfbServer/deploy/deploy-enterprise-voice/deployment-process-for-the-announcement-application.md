---
title: Processo di distribuzione per l'applicazione Annuncio in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processo di distribuzione e passaggi per l'applicazione Annuncio in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812306"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="f898b-103">Processo di distribuzione per l'applicazione Annuncio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f898b-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="f898b-104">Processo di distribuzione e passaggi per l'applicazione Annuncio in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f898b-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f898b-105">L'applicazione Annuncio è una funzionalità di VoIP aziendale che consente di configurare cosa accade alle chiamate a estensioni non assegnate (estensioni valide per l'organizzazione, ma non assegnate a una persona o a un telefono).</span><span class="sxs-lookup"><span data-stu-id="f898b-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="f898b-106">È ad esempio possibile configurare le chiamate a numeri non assegnati in modo che venga riprodotto un messaggio, in modo che vengano trasferite a un'altra destinazione oppure in modo che vengano eseguite entrambe queste azioni.</span><span class="sxs-lookup"><span data-stu-id="f898b-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="f898b-107">L'applicazione Annuncio viene installata come caratteristica dell'applicazione Response Group nel Front End Server o nel server Standard Edition quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f898b-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f898b-108">È necessario configurare gli annunci caricando i file audio oppure configurando la sintesi vocale e la tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="f898b-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="f898b-109">In questa sezione viene fornita una panoramica dei passaggi necessari per distribuire l'applicazione Annuncio.</span><span class="sxs-lookup"><span data-stu-id="f898b-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="f898b-110">È necessario distribuire VoIP aziendale prima di configurare gli annunci.</span><span class="sxs-lookup"><span data-stu-id="f898b-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="f898b-111">I componenti richiesti dall'applicazione Annuncio vengono installati e abilitati quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f898b-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="f898b-112">**Processo di distribuzione degli annunci**</span><span class="sxs-lookup"><span data-stu-id="f898b-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="f898b-113">**Fase**</span><span class="sxs-lookup"><span data-stu-id="f898b-113">**Phase**</span></span>|<span data-ttu-id="f898b-114">**Procedura**</span><span class="sxs-lookup"><span data-stu-id="f898b-114">**Steps**</span></span>|<span data-ttu-id="f898b-115">**Ruoli**</span><span class="sxs-lookup"><span data-stu-id="f898b-115">**Roles**</span></span>|<span data-ttu-id="f898b-116">**Documentazione relativa alla distribuzione**</span><span class="sxs-lookup"><span data-stu-id="f898b-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f898b-117">Configurazione delle impostazioni degli annunci</span><span class="sxs-lookup"><span data-stu-id="f898b-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="f898b-118">Creare l'annuncio registrando e caricando file audio o tramite sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="f898b-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="f898b-119">Configurare gli intervalli di numeri non assegnati nella tabella dei numeri non assegnati e associarli all'annuncio appropriato.</span><span class="sxs-lookup"><span data-stu-id="f898b-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="f898b-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f898b-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="f898b-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f898b-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="f898b-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f898b-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="f898b-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f898b-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="f898b-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="f898b-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="f898b-125">Creare o eliminare un annuncio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f898b-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="f898b-126">Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f898b-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="f898b-127">Verifica della distribuzione degli annunci</span><span class="sxs-lookup"><span data-stu-id="f898b-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="f898b-128">Testare ascoltando annunci per verificare che la configurazione funzioni nel modo previsto.</span><span class="sxs-lookup"><span data-stu-id="f898b-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="f898b-129">(Facoltativo) Verificare la distribuzione degli annunci in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f898b-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

