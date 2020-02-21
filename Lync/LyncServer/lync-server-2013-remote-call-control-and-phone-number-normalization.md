---
title: 'Lync Server 2013: controllo delle chiamate remote e normalizzazione del numero di telefono'
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
ms.openlocfilehash: e9acca7ab40ea8c6af3488c454620d20f1e9e326
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Controllo delle chiamate remote e normalizzazione del numero di telefono in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-22_

I client Lync scaricano le regole di normalizzazione dei numeri di telefono come parte del download di file del servizio Rubrica (ABS). Negli scenari con controllo delle chiamate remote le regole di normalizzazione dei numeri di telefono del servizio Rubrica vengono applicate sia alle chiamate in arrivo che alle chiamate in uscita con tale controllo abilitato. Per le chiamate in arrivo dirette a un utente abilitato per l'utilizzo del controllo delle chiamate remote, il numero di telefono del chiamate viene innanzitutto normalizzato nel formato E.164 dal gateway SIP/CSTA o dal centralino (PBX). Quando Lync Server 2013 riceve la chiamata dal gateway, esegue la ricerca di numeri inversi (inversa) sul numero di telefono del chiamante rispetto al numero normalizzato nell'elenco contatti di Microsoft Office Outlook del destinatario della chiamata o nell'elenco indirizzi globale memorizzato in Servizio Rubrica. Se tale ricerca trova una corrispondenza, il chiamante viene identificato in base al nome nella notifica della chiamata in arrivo.

Per le chiamate di controllo delle chiamate remote in uscita, Lync applica le regole di normalizzazione dei numeri di telefono del servizio Rubrica al numero composto prima di instradare la chiamata al gateway SIP/CSTA.

Per informazioni dettagliate sulla creazione di regole di normalizzazione dei numeri di telefono per il controllo delle chiamate remote, vedere [dial plans and normalizzation Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Migrazione delle regole di normalizzazione dei numeri di telefono

Se si esegue la migrazione di utenti precedentemente abilitati per il controllo delle chiamate remote, vedere gli argomenti seguenti nella documentazione relativa alla migrazione:

  - Per Lync Server 2010, vedere [migrate Address Book](migrate-address-book.md) nella documentazione relativa alla migrazione.

  - Per Communications Server 2007 R2, vedere [migrate Address Book](migrate-address-book_1.md) nella documentazione relativa alla migrazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

