---
title: 'Lync Server 2013: Controllo delle chiamate remote e normalizzazione dei numeri di telefono'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eff9fb48e9730549d67638c69d8655d8f04d710
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Controllo delle chiamate remote e normalizzazione dei numeri di telefono in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-22_

I client Lync scaricano le regole di normalizzazione dei numeri di telefono come parte del download di file in ABS (Address Book Service). Negli scenari di controllo delle chiamate remote, le regole di normalizzazione del numero di telefono del servizio Rubrica vengono applicate alle chiamate di controllo delle chiamate remote in entrata e in uscita. Per le chiamate in arrivo a un utente abilitato per il controllo delle chiamate remote, il numero di telefono del chiamante viene normalizzato per la prima volta in formato E. 164 tramite il gateway SIP/CSTA o il PBX (Private Branch Exchange). Quando Lync Server 2013 riceve la chiamata dal gateway, esegue la ricerca di numeri inversa (RNL) sul numero di telefono del chiamante rispetto al numero normalizzato nell'elenco contatti di Microsoft Office Outlook o nell'elenco indirizzi globale archiviato in Servizio Rubrica. Se la ricerca con numero inverso trova una corrispondenza, il chiamante viene identificato per nome nella notifica di chiamata in arrivo.

Per le chiamate di controllo delle chiamate remote in uscita, Lync applica le regole di normalizzazione del numero di telefono del servizio Rubrica al numero composto prima di instradare la chiamata al gateway SIP/CSTA.

Per informazioni dettagliate sulla creazione di regole di normalizzazione dei numeri di telefono per il controllo delle chiamate remote, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Migrazione delle regole di normalizzazione dei numeri di telefono

Se si esegue la migrazione degli utenti abilitati in precedenza per il controllo delle chiamate remote, vedere gli argomenti seguenti nella documentazione relativa alla migrazione:

  - Per Lync Server 2010, vedere [eseguire la migrazione della rubrica](migrate-address-book.md) nella documentazione relativa alla migrazione.

  - Per Communications Server 2007 R2, vedere [eseguire la migrazione della rubrica](migrate-address-book_1.md) nella documentazione di migrazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

