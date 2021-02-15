---
title: Integrare Skype for Business Server con Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Riepilogo: esaminare i passaggi di integrazione per Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.'
ms.openlocfilehash: 6b5c63c0ad6783c11fd8fde25d1b00dc84d7e15a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833736"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="16641-103">Integrare Skype for Business Server con Exchange Server</span><span class="sxs-lookup"><span data-stu-id="16641-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="16641-104">**Riepilogo:** Esaminare i passaggi di integrazione Exchange Server 2013 o versione successiva e Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="16641-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="16641-105">Exchange Server 2013 o versioni successive e Skype for Business Server sono compatibili e integrati.</span><span class="sxs-lookup"><span data-stu-id="16641-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="16641-106">Ad esempio, le informazioni sulla presenza degli utenti di Skype for Business possono essere segnalate in Microsoft Outlook; Analogamente, Skype for Business può accedere al calendario di Outlook di un utente, notare che l'utente ha una riunione pianificata e mostrare la presenza dell'utente come Occupato durante la riunione.</span><span class="sxs-lookup"><span data-stu-id="16641-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="16641-107">Anche se non è necessario eseguire Exchange Server per eseguire Skype for Business Server (o viceversa), i due prodotti insieme migliorano l'esperienza utente reciproca.</span><span class="sxs-lookup"><span data-stu-id="16641-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="16641-108">Questa documentazione fornisce informazioni sull'integrazione di Skype for Business Server e Exchange Server 2016 o Exchange Server 2013, ma presuppone che la configurazione e la configurazione iniziali di questi due prodotti siano già state completate.</span><span class="sxs-lookup"><span data-stu-id="16641-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="16641-109">Per informazioni dettagliate sulla distribuzione di Skype for Business Server, vedere il [Tech Center di Skype for Business Server.](https://go.microsoft.com/fwlink/p/?LinkId=246127)</span><span class="sxs-lookup"><span data-stu-id="16641-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="16641-110">Per informazioni dettagliate sulla Exchange Server vedere la documentazione relativa alla distribuzione per la versione di Exchange in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="16641-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="16641-111">Se si sta integrando un'installazione locale di Skype for Business Server con Microsoft Exchange Online, vedere Configurare l'integrazione tra Skype for Business Server locale e [Outlook Web App.](outlook-web-app.md)</span><span class="sxs-lookup"><span data-stu-id="16641-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="16641-112">Se si sta integrando Skype for Business online con Exchange Server locale, vedere Configurare OAuth tra Skype for Business online ed [Exchange locale.](oauth-with-online-and-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="16641-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="16641-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="16641-113">In this section</span></span>

[<span data-ttu-id="16641-114">Configurare le applicazioni partner in Skype for Business Server e Exchange Server</span><span class="sxs-lookup"><span data-stu-id="16641-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="16641-115">Configurare Skype for Business Server per l'utilizzo Exchange Server archiviazione</span><span class="sxs-lookup"><span data-stu-id="16641-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="16641-116">Configurare SharePoint Server per cercare i dati archiviati di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="16641-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="16641-117">Configurare Skype for Business Server per l'utilizzo dell'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="16641-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="16641-118">Configurare l'uso di foto ad alta risoluzione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="16641-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="16641-119">Configurare Exchange Server messaggistica unificata per la segreteria telefonica di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="16641-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="16641-120">Integrazione di Skype for Business Server e Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="16641-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="16641-121">Configurare l'archivio contatti personali nei computer client per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="16641-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="16641-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16641-122">See also</span></span>

[<span data-ttu-id="16641-123">Pianificare l'integrazione di Skype for Business ed Exchange</span><span class="sxs-lookup"><span data-stu-id="16641-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
