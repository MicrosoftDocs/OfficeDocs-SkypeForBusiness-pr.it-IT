---
title: 'Lync Server 2013: creazione o modifica di una nuova chat room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 564db7b9d1bfaab00e51628377f330da05af17e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Creazione o modifica di una nuova sala in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-03-19_

La configurazione delle chat room permanenti è in genere gestita dagli utenti. un amministratore di chat persistente in genere non configura o gestisce le chat room. I cmdlet di Windows PowerShell per la gestione delle chat sono disponibili solo per gli amministratori di **ruolo CsPersistentChatAdministrator** .

Gli utenti che sono **creatori** di una determinata categoria possono utilizzare il client Lync per creare e gestire le chat room. Gli utenti designati come responsabili di una specifica chat room possono inoltre occuparsi della gestione continuata della chat room, ad esempio modificandone le proprietà o i membri.

<div>


> [!TIP]  
> Gli amministratori di chat persistente possono anche essere creatori e non sono soggetti alle restrizioni applicate ai creatori.



</div>

Facoltativamente, se si è un amministratore di chat persistente, è possibile utilizzare un'interfaccia utente per creare e gestire le chat room invece di usare i cmdlet di Windows PowerShell. A tale scopo, abilitare SIP un amministratore per il server Chat persistente e quindi utilizzare il client Lync per creare e gestire le chat room.

Se si desidera creare un flusso di lavoro per la gestione delle sale personalizzato per gli utenti, è possibile impostare la proprietà **RoomManagementUrl** nella configurazione del server Chat persistente per reindirizzare gli utenti alla soluzione personalizzata dal client Lync.

Per informazioni dettagliate sulla configurazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere la sezione "gestione sala" in [configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Per informazioni dettagliate sulla configurazione delle chat room, vedere [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.

<div>


> [!NOTE]  
> Il server Chat persistente consente agli utenti di creare e gestire la chat room per un sito specifico. Tuttavia, gli utenti non possono creare o gestire chat room su altri siti all'interno della stessa topologia. Assicurarsi di specificare i creatori e i responsabili delle chat room per tutti i siti dell'organizzazione.



</div>

<div>


> [!NOTE]  
> Gli utenti ospitati in un Survivable Branch Appliance di Lync Server non sono in grado di creare nuove chat room o di visualizzare la scheda sala per le sale esistenti.



</div>

</div>

<span> </span>

</div>

</div>

</div>

