---
title: Creare un amministratore di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Riepilogo: leggere questo argomento per informazioni su come creare un ruolo di amministratore del server di chat persistente per abilitare la configurazione e la gestione iniziali dei servizi di chat persistenti in Skype for Business Server 2015.'
ms.openlocfilehash: 3692169a65d73c3951ce58e77b132a4f118c54e9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239770"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="60c7e-103">Creare un amministratore di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="60c7e-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="60c7e-104">**Riepilogo:** Leggere questo argomento per informazioni su come creare un ruolo di amministratore del server di chat persistente per abilitare la configurazione e la gestione iniziali dei servizi di chat persistenti in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="60c7e-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="60c7e-105">In Skype for Business Server gli utenti che eseguono attività specifiche devono essere assegnati come membri di uno o più gruppi specifici.</span><span class="sxs-lookup"><span data-stu-id="60c7e-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="60c7e-106">Il controllo di accesso basato sui ruoli (RBAC) viene usato per concedere privilegi assegnando agli utenti i ruoli amministrativi predefiniti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="60c7e-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="60c7e-107">Questi ruoli corrispondono ai gruppi di sicurezza universale in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="60c7e-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="60c7e-108">Ai membri del gruppo di sicurezza dell'amministratore della chat persistente, CsPersistentChatAdministrator, viene concesso l'accesso ai cmdlet del server di chat persistente, che possono essere eseguiti con Skype for Business Server Management Shell o con Skype for business Pannello di controllo server.</span><span class="sxs-lookup"><span data-stu-id="60c7e-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="60c7e-109">Prima di configurare e amministrare il server di chat persistente, assicurati che siano presenti i diritti e le autorizzazioni degli utenti appropriati e che tutti gli utenti che agiscono come amministratori della chat persistente vengano aggiunti al gruppo di sicurezza dell'amministratore della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="60c7e-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="60c7e-110">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="60c7e-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="60c7e-111">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="60c7e-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="60c7e-112">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="60c7e-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="60c7e-113">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="60c7e-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="60c7e-114">Creare un amministratore di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="60c7e-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="60c7e-115">Per aggiungere un utente al gruppo di sicurezza dell'amministratore della chat persistente, CsPersistentChatAdministrator, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="60c7e-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="60c7e-116">Utilizzando un account che disponga delle autorizzazioni per modificare l'appartenenza a un gruppo di Active Directory, accedere a un computer in cui sono stati installati utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="60c7e-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="60c7e-117">Fare clic sul pulsante Start, scegliere tutti i programmi, strumenti di amministrazione e quindi fare clic su utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="60c7e-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="60c7e-118">In utenti e computer di Active Directory espandere il nome del dominio e fare clic sul contenitore utenti.</span><span class="sxs-lookup"><span data-stu-id="60c7e-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="60c7e-119">Fare clic con il pulsante destro del mouse sul gruppo di sicurezza CsPersistentChatAdministrator e quindi scegliere Proprietà.</span><span class="sxs-lookup"><span data-stu-id="60c7e-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="60c7e-120">Nella scheda membri della finestra di dialogo Proprietà fare clic su Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="60c7e-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="60c7e-121">Nella finestra di dialogo Seleziona utenti, computer, contatto o gruppi digitare il nome utente o il nome visualizzato dell'utente da aggiungere al gruppo nella casella Immettere i nomi degli oggetti da selezionare e quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="60c7e-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="60c7e-122">Nella finestra di dialogo Proprietà fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="60c7e-122">In the Properties dialog box, click OK.</span></span>
    

