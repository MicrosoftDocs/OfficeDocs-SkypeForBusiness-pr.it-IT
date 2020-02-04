---
title: Informazioni sull'appartenenza di Chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b4eb5fbe4342c1bd6bcb3bbb842e076e5863ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>Informazioni sull'appartenenza di Chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

L'accesso degli utenti alle chat room permanenti viene gestito dall'appartenenza; Gli utenti devono essere membri di una chat room per poter pubblicare e leggere i messaggi. Solo i **relatori** con un'affiliazione designata con chat room possono usare la **registrazione nelle sale dell'Auditorium**. Un auditorium è un tipo di chat room (l'altro è **normale**), dove possono essere pubblicati solo relatori e tutti possono leggere.

Inoltre, le chat room permanenti funzionano in base alle regole di una categoria. Per informazioni dettagliate sulle categorie, vedere [gestione di categorie, sale e componenti aggiuntivi in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)e anche le sezioni "come funziona l'ambito della categoria" e "strategie per la categoria della sala" più avanti in questo argomento.

Un amministratore della chat persistente può creare e gestire le categorie delle chat room. Nell'ambito della creazione e della gestione delle categorie di chat room, l'amministratore della chat persistente può configurare le entità (gruppi, contenitori e utenti di servizi di dominio Active Directory) che hanno accesso a membri o creatori di chat room di una specifica categoria.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Servizi di dominio Active Directory e chat persistenti

Il server di chat persistente si basa su Active Directory per il pool di utenti di chat permanenti interni. Dopo aver installato la chat persistente (client), è possibile aggiungere i domini di utenti e gruppi utenti alla categoria sala. È quindi possibile aggiungere questi utenti e gruppi all'appartenenza delle categorie della sala.

<div>


> [!IMPORTANT]  
> Devi assicurarti che non ci siano nomi duplicati per gli utenti che vogliono apportare modifiche alle chat room persistenti. Se sono presenti nomi utente duplicati, modificarli in nomi diversi per sbloccare gli utenti da apportare tali modifiche. Se un utente ha nomi duplicati in Active Directory e prova a apportare modifiche nelle rispettive sale, viene visualizzato un messaggio di errore che chiede all'utente di contattare l'amministratore per la risoluzione.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>Funzionamento dell'ambito delle categorie

Una categoria specifica tutti gli utenti e i gruppi che possono essere membri in un elenco di appartenenza di una chat room persistente in quella categoria, in base alla relativa proprietà **AllowedMembers** . Se ad esempio si imposta la **AllowedMembers** della categoria su contoso.com, è possibile aggiungere un gruppo o un utente a *Contoso* come membro delle chat room della categoria. Se si imposta **AllowedMembers** su una categoria per le *vendite*, solo i gruppi e gli utenti della lista di distribuzione possono essere aggiunti come membri alle chat room della categoria. Analogamente, la proprietà **Creators** consente di controllare chi può creare chat room in quella categoria. Dopo la creazione della chat room, tutti i membri del gruppo **AllowedMembers** possono essere designati come **Manager** per le operazioni di gestione in corso nelle sale, ad esempio per le modifiche e le approvazioni.

La definizione di **AllowedMembers** e **Creators** per una categoria ha i vantaggi seguenti:

  - Tutte le chat room di questa categoria sono associate alle restrizioni impostate a livello di categoria. Puoi usare questa funzione per separare le chat room in base alle esigenze aziendali e ai criteri di accesso.

  - Un utente nell'elenco **Creators** può creare nuove chat room in quella categoria. Se vuoi implementare un sistema in cui un numero limitato di personale dell'organizzazione può creare chat room, questo controllo può essere usato per soddisfare tale requisito.

</div>

<div>

## <a name="room-category-strategies"></a>Strategie per le categorie di camere

Il **AllowedMembers** di una categoria deve includere tutti gli utenti che useranno qualsiasi chat room persistente in questa categoria. A seconda dei requisiti per proteggere i dati aziendali e garantire il livello di accesso appropriato, è consigliabile definire una o più categorie per specificare chi può cercare e partecipare alle sale. Se si vuole consentire solo un determinato set di utenti (helpdesk centrale o solo dipendenti a tempo pieno) per la creazione di sale, è possibile applicare l'ambito agli **autori** di una categoria per soddisfare tale requisito.

Le categorie possono essere usate anche per creare muri etici. I muri etici impediscono qualsiasi conflitto di interessi in un'organizzazione. Ad esempio, un amministratore può creare chat room in una categoria solo per gli operatori commerciali, mentre le chat room in un'altra categoria possono essere usate solo dagli analisti.

<div>


> [!NOTE]  
> In Lync Server 2013, Persistent Chat Server, non è supportato l'accesso agli utenti federati. Se sono presenti chat provenienti da utenti federati nelle versioni precedenti del server di chat persistente, verranno migrati. Gli utenti federati vengono aggiunti come entità disabilitate.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>Restringere i membri ai gruppi di utenti

Quando si aggiunge un dominio a una categoria, i gruppi di utenti il cui oggetto gruppo è contenuto in tale dominio sono disponibili in modo che sia possibile specificarli come membri di sale della categoria.

Come regola generale, è consigliabile usare i contenitori di Active Directory, ad esempio i domini e le unità organizzative, per definire i **AllowedMembers** e i **creatori**di una categoria. Puoi aggiungere oggetti da qualsiasi dominio a un elenco **AllowedMembers** o **Creators** . Solo gli oggetti inclusi nell'elenco **AllowedMembers** o **Creators** possono essere aggiunti alle sale di tale categoria.

</div>

</div>

<span> </span>

</div>

</div>

</div>

