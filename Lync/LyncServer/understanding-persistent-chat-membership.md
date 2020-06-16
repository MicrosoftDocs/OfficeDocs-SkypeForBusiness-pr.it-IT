---
title: Informazioni sull'appartenenza di chat persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400866812ab2d5efb12960dc3c2f37c2fcb8eb45
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>Informazioni sull'appartenenza di chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

L'accesso degli utenti alle chat room permanenti è gestito dall'appartenenza; Gli utenti devono essere membri di una chat room per poter postare e leggere i messaggi. Solo i **relatori** con un'affiliazione designata alle chat room possono utilizzare la **pubblicazione nelle sale auditorium**. Un auditorium è un tipo di chat room (l'altro è **normale**), in cui solo i relatori possono pubblicare e in cui tutti possono leggere.

Inoltre, le chat room persistenti operano secondo le regole di una categoria. Per informazioni dettagliate sulle categorie, vedere [Managing Categories, rooms, and Add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), nonché le sezioni "come funziona l'ambito delle categorie" e "strategie di categoria della sala" più avanti in questo argomento.

Un amministratore di chat persistente può creare e gestire le categorie delle chat room. Durante la creazione e la gestione delle categorie di chat room, l'amministratore di chat persistente può configurare le entità (gruppi di servizi di dominio Active Directory, contenitori e utenti) che hanno accesso ai membri o ai creatori delle chat room di una categoria specifica.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Servizi di dominio Active Directory e chat persistente

Il server Chat persistente si basa su Active Directory per il pool di utenti di chat permanenti interni. Dopo l'installazione di Persistent Chat (client), è possibile aggiungere domini di utenti e gruppi utente alla categoria sala. È quindi possibile aggiungere questi utenti e gruppi all'appartenenza delle categorie di chat room.

<div>


> [!IMPORTANT]  
> È necessario assicurarsi che non vi siano nomi duplicati per gli utenti che desiderano apportare modifiche alle chat room persistente. Se sono presenti nomi duplicati, modificarli per consentire agli utenti di apportare le modifiche. Se un utente ha nomi duplicati in Active Directory e cerca di apportare modifiche nelle rispettive sale, verrà visualizzato un messaggio di errore che richiede all'utente di contattare l'amministratore per la risoluzione.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>Funzionamento degli ambiti delle categorie

Una categoria specifica tutti gli utenti e i gruppi che possono essere membri di un elenco di appartenenze di una chat room persistente in quella categoria, in base alla relativa proprietà **AllowedMembers** . Ad esempio, se si imposta la categoria **AllowedMembers** su contoso.com, è possibile aggiungere qualsiasi gruppo o utente a *Contoso* come membro delle chat room della categoria. Se si imposta la proprietà **AllowedMembers** di una categoria su *Vendite* solo i gruppi e gli utenti di questa lista di distribuzione potranno essere aggiunti come membri delle chat room della categoria. Analogamente la proprietà **Creators** consente di controllare chi può creare le chat room nella categoria. Dopo aver creato una chat room, chiunque appartenga al gruppo di **AllowedMembers** può essere designato come **responsabile** per la gestione delle chat room (ad esempio, modifiche e approvazioni alle appartenenze).

La definizione di **AllowedMembers** e **Creators** per una categoria ha i vantaggi seguenti:

  - All chat rooms in this category are bound by the restrictions set at the category level. You can use this to segregate chat rooms based on business need and access policies.

  - A user who is in the **Creators** list can create new chat rooms in that category. If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.

</div>

<div>

## <a name="room-category-strategies"></a>Strategie per le categorie di chat room

Il **AllowedMembers** di una categoria deve includere tutti gli utenti che utilizzeranno qualsiasi chat room persistente in questa categoria. A seconda dei requisiti di protezione dei dati aziendali e di verifica del livello appropriato di accesso, è possibile definire una o più categorie per specificare chi può cercare e partecipare alle chat room. Se si vuole consentire solo a un determinato set di utenti (un helpdesk centrale o solo i dipendenti a tempo pieno) di creare chat room, è possibile limitare l'ambito di utenti **Creator** di una categoria in modo conseguente.

Categories can also be used to create ethical walls. Ethical walls prevent any conflict of interest in an organization. For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.

<div>


> [!NOTE]  
> In Lync Server 2013, il server Chat persistente non supporta l'accesso agli utenti federati. Se sono presenti chat da parte di utenti federati nelle versioni precedenti del server Chat persistente, verranno migrate. Gli utenti federati vengono aggiunti come entità disabilitate.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>Limitazione dei membri a gruppi di utenti

Quando si aggiunge un dominio all'ambito della categoria radice, i gruppi di utenti i cui oggetti gruppo sono inclusi in tale dominio vengono resi disponibili per essere specificati come membri delle chat room nella categoria in questione.

È consigliabile, come regola generale, utilizzare i contenitori di Active Directory, ad esempio i domini e le unità organizzative, per la definizione di **AllowedMembers** e dei **creatori**di una categoria. È possibile aggiungere oggetti di qualsiasi dominio a un elenco **AllowedMembers** o **Creators**. Solo gli oggetti negli elenchi **AllowedMembers** e **Creators** possono essere aggiunti alle chat room nella categoria.

</div>

</div>

<span> </span>

</div>

</div>

</div>

