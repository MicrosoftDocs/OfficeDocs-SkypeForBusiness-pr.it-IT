---
title: 'Lync Server 2013: Creazione o modifica di una nuova chat room'
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
ms.openlocfilehash: 7bd0fdbce300f417764e093fec3acb8705b2d17b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Creazione o modifica di una nuova chat room in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-03-19_

La configurazione delle chat room permanenti viene comunemente gestita dagli utenti; un amministratore della chat persistente in genere non configura né gestisce le chat room. I cmdlet di Windows PowerShell per la gestione delle sale sono disponibili solo per gli amministratori di **CsPersistentChatAdministrator** .

Gli utenti che sono **creatori** in una determinata categoria possono usare il client Lync per creare e gestire le sale. Gli utenti designati come responsabili di una chat room possono anche eseguire la gestione della sala, ad esempio modificare le proprietà della sala o l'appartenenza.

<div>


> [!TIP]  
> Gli amministratori della chat persistente possono essere anche creatori e non sono soggetti alle restrizioni imposte ai creatori.



</div>

Facoltativamente, se si è un amministratore di chat persistente, è possibile usare un'interfaccia utente per creare e gestire le chat room anziché i cmdlet di Windows PowerShell. A tale scopo, abilitare SIP per un amministratore per il server di chat persistente e quindi usare il client Lync per creare e gestire chat room.

Se si vuole creare un flusso di lavoro personalizzato per la gestione delle room per gli utenti, è possibile impostare la proprietà **RoomManagementUrl** sulla configurazione del server di chat persistente per reindirizzare gli utenti alla soluzione personalizzata dal client Lync.

Per informazioni dettagliate sulla configurazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere "gestione sala" nella [configurazione del server di chat persistente usando i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Per informazioni dettagliate sulla configurazione delle chat room, vedere [configurare le sale in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.

<div>


> [!NOTE]  
> Il server di chat persistente consente agli utenti di creare e gestire chat room per un sito specifico. Gli utenti non possono tuttavia creare o gestire chat room in altri siti all'interno della stessa topologia. Assicurati di specificare i creatori e i responsabili della chat room per tutti i siti dell'organizzazione.



</div>

<div>


> [!NOTE]  
> Gli utenti ospitati in un dispositivo Survivable Branch di Lync Server non riescono a creare nuove chat room o a visualizzare la scheda della sala per le camere esistenti.



</div>

</div>

<span> </span>

</div>

</div>

</div>

