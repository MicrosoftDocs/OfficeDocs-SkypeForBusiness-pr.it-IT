---
title: Processo di distribuzione per l'applicazione di annuncio in Skype for Business Server
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
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processo di distribuzione e passaggi per l'applicazione di annunci in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 89f01ed4c9488aa74b07bfae41f3bf27032b552e
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767399"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="c9260-103">Processo di distribuzione per l'applicazione di annuncio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9260-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="c9260-104">Processo di distribuzione e passaggi per l'applicazione di annunci in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c9260-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c9260-105">L'applicazione di annuncio è una caratteristica di VoIP aziendale che consente di configurare le chiamate alle estensioni non assegnate (estensioni valide per l'organizzazione, ma non assegnate a una persona o a un telefono).</span><span class="sxs-lookup"><span data-stu-id="c9260-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="c9260-106">Ad esempio, puoi configurare le chiamate a numeri non assegnati per riprodurre un messaggio o per essere trasferito a una destinazione diversa o entrambe.</span><span class="sxs-lookup"><span data-stu-id="c9260-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="c9260-107">L'applicazione annuncio viene installata come caratteristica dell'applicazione Response Group nel server front-end o Standard Edition quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c9260-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c9260-108">È necessario configurare gli annunci caricando i file audio o configurando la sintesi vocale (TTS) e configurando la tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="c9260-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="c9260-109">Questa sezione fornisce una panoramica dei passaggi necessari per la distribuzione dell'applicazione di annunci.</span><span class="sxs-lookup"><span data-stu-id="c9260-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="c9260-110">È necessario distribuire Enterprise Voice prima di configurare gli annunci.</span><span class="sxs-lookup"><span data-stu-id="c9260-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="c9260-111">I componenti necessari per l'applicazione di annuncio vengono installati e abilitati quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c9260-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="c9260-112">**Processo di distribuzione degli annunci**</span><span class="sxs-lookup"><span data-stu-id="c9260-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="c9260-113">**Fase**</span><span class="sxs-lookup"><span data-stu-id="c9260-113">**Phase**</span></span>|<span data-ttu-id="c9260-114">**Passaggi**</span><span class="sxs-lookup"><span data-stu-id="c9260-114">**Steps**</span></span>|<span data-ttu-id="c9260-115">**Ruoli**</span><span class="sxs-lookup"><span data-stu-id="c9260-115">**Roles**</span></span>|<span data-ttu-id="c9260-116">**Documentazione di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="c9260-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c9260-117">Configurare le impostazioni degli annunci</span><span class="sxs-lookup"><span data-stu-id="c9260-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="c9260-118">Creare l'annuncio registrando e caricando i file audio o tramite sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="c9260-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="c9260-119">Configurare gli intervalli di numeri non assegnati nella tabella dei numeri non assegnati e associarli con l'annuncio appropriato.</span><span class="sxs-lookup"><span data-stu-id="c9260-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="c9260-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c9260-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="c9260-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c9260-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="c9260-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c9260-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="c9260-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c9260-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="c9260-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="c9260-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="c9260-125">Creare o eliminare un annuncio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9260-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="c9260-126">Creare o modificare un intervallo di numeri non assegnati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9260-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="c9260-127">Verificare la distribuzione degli annunci</span><span class="sxs-lookup"><span data-stu-id="c9260-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="c9260-128">Eseguire il test ascoltando gli annunci per verificare che la configurazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="c9260-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="c9260-129">Opzionale Verificare la distribuzione degli annunci in Skype for business</span><span class="sxs-lookup"><span data-stu-id="c9260-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

