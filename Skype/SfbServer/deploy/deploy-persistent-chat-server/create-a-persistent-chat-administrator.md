---
title: Creare un amministratore di Persistent Chat in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Riepilogo: leggere questo argomento per informazioni su come creare un ruolo di amministratore del server Chat persistente per abilitare la configurazione iniziale e la gestione dei servizi chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802096"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="74c2a-103">Creare un amministratore di Persistent Chat in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="74c2a-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="74c2a-104">**Riepilogo:** Leggere questo argomento per informazioni su come creare un ruolo di amministratore del server Chat persistente per abilitare la configurazione iniziale e la gestione dei servizi chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="74c2a-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="74c2a-105">In Skype for Business Server, gli utenti che eseguono attività specifiche devono essere assegnati come membri di uno o più gruppi specifici.</span><span class="sxs-lookup"><span data-stu-id="74c2a-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="74c2a-106">Role-Based controllo di accesso predefinito (RBAC, Access Control) viene utilizzato per concedere privilegi assegnando gli utenti ai ruoli amministrativi predefiniti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="74c2a-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="74c2a-107">Questi ruoli corrispondono ai gruppi di sicurezza universali in Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74c2a-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="74c2a-108">Ai membri del gruppo di sicurezza Amministratore chat persistente, CsPersistentChatAdministrator, viene concesso l'accesso ai cmdlet del server Chat persistente, che possono essere eseguiti utilizzando Skype for Business Server Management Shell o il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="74c2a-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="74c2a-109">Prima di configurare e amministrare il server Chat persistente, verificare che siano presenti le autorizzazioni e i diritti utente appropriati e che tutti gli utenti che fungeranno da amministratori di Chat persistente siano aggiunti al gruppo di protezione Amministratore chat persistente.</span><span class="sxs-lookup"><span data-stu-id="74c2a-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="74c2a-110">La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="74c2a-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="74c2a-111">Le stesse funzionalità sono disponibili in Teams.</span><span class="sxs-lookup"><span data-stu-id="74c2a-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="74c2a-112">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="74c2a-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="74c2a-113">Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="74c2a-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="74c2a-114">Creare un amministratore di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="74c2a-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="74c2a-115">Per aggiungere un utente al gruppo di sicurezza Amministratore di Persistent Chat, CsPersistentChatAdministrator, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="74c2a-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="74c2a-116">Utilizzando un account che dispone dell'autorizzazione per modificare l'appartenenza a un gruppo di Active Directory, accedere a un computer in cui sono stati installati Utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74c2a-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="74c2a-117">Fare clic sul pulsante Start, scegliere Tutti i programmi, Strumenti di amministrazione e quindi Utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74c2a-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="74c2a-118">In Utenti e computer di Active Directory espandere il nome del dominio e fare clic sul contenitore degli utenti.</span><span class="sxs-lookup"><span data-stu-id="74c2a-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="74c2a-119">Fare clic con il pulsante destro del mouse sul gruppo di sicurezza CsPersistentChatAdministrator e quindi scegliere Proprietà.</span><span class="sxs-lookup"><span data-stu-id="74c2a-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="74c2a-120">Nella finestra di dialogo Proprietà fare clic su Aggiungi nella scheda Membri.</span><span class="sxs-lookup"><span data-stu-id="74c2a-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="74c2a-121">Nella finestra di dialogo Seleziona utenti, computer, contatti o gruppi digitare il nome utente o il nome visualizzato dell'utente da aggiungere al gruppo nella casella Immettere i nomi degli oggetti da selezionare e quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="74c2a-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="74c2a-122">Nella finestra di dialogo Proprietà fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="74c2a-122">In the Properties dialog box, click OK.</span></span>
    

