---
title: Assegnazione di un certificato di autenticazione da server a server a Lync Server 2013
description: Assegnazione di un certificato di autenticazione da server a server a Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 042158167f89dc2b6e743e8db94149d4f1cbc1a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560542"
---
# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>Assegnazione di un certificato di autenticazione da server a server a Microsoft Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-24_

Per determinare se un certificato di autenticazione da server a server è già stato assegnato a Microsoft Lync Server 2013, eseguire il comando seguente da Lync Server 2013 Management Shell:

    Get-CsCertificate -Type OAuthTokenIssuer

Se non vengono restituite informazioni sui certificati, è necessario assegnare un certificato dell'autorità emittente di token prima di poter utilizzare l'autenticazione da server a server. Come regola generale, qualsiasi certificato di Lync Server 2013 può essere utilizzato come certificato di OAuthTokenIssuer. ad esempio, il certificato predefinito di Lync Server 2013 può essere utilizzato anche come certificato di OAuthTokenIssuer. Il certificato OAUthTokenIssuer può anche essere qualsiasi certificato del server Web che include il nome del dominio SIP nel campo Subject. I due requisiti principali per il certificato utilizzato per l'autenticazione da server a server sono i seguenti: 1) lo stesso certificato deve essere configurato come certificato OAuthTokenIssuer su tutti i Front End Server; 2) il certificato deve essere almeno pari a 2048 bit.

Se non si dispone di un certificato da utilizzare per l'autenticazione da server a server, è possibile ottenere un nuovo certificato, importarlo e quindi utilizzarlo per l'autenticazione da server a server. Dopo aver richiesto e ottenuto il nuovo certificato, è possibile accedere a uno dei Front End Server e utilizzare un comando di Windows PowerShell simile al seguente per importare e assegnare il certificato:

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

Nel comando precedente il parametro Path rappresenta il percorso completo del file di certificato e il parametro Password rappresenta la password assegnata al certificato. Questa procedura deve essere eseguita una sola volta. Il servizio di replica di Lync Server creerà quindi automaticamente un insieme di attività pianificate per decrittografare e distribuire il certificato in tutti i Front End Server.

In alternativa, è possibile utilizzare come certificato di autenticazione da server a server un certificato esistente. Come già specificato, è possibile utilizzare a tale scopo il certificato predefinito. La coppia seguente di comandi di Windows PowerShell recupera il valore della proprietà Thumbprint del certificato predefinito e quindi utilizza tale valore per impostare il certificato predefinito come certificato di autenticazione da server a server:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

Nel comando precedente il certificato recuperato viene configurato in modo da funzionare come certificato di autenticazione da server a server globale. In questo modo il certificato verrà replicato in tutti i Front End Server e da essi utilizzato. Come già specificato, questo comando deve essere eseguito una sola volta e solo in un Front End Server. Anche se tutti i Front End Server devono utilizzare lo stesso certificato, non è necessario configurare il certificato OAuthTokenIssuer in ognuno di essi. Sarà sufficiente configurarlo una volta e quindi il server di replica di Lync Server lo copierà in ogni server.

Il cmdlet Set-CsCertificate prende il certificato in questione e configura immediatamente il certificato in modo che funga da certificato OAuthTokenIssuer corrente. (Lync Server 2013 conserva due copie di un tipo di certificato: il certificato corrente e il certificato precedente). Se è necessario che il nuovo certificato cominci subito a fungere da certificato OAuthTokenIssuer, è necessario utilizzare il cmdlet Set-CsCertificate.

È inoltre possibile utilizzare il cmdlet Set-CsCertificate per distribuire un nuovo certificato, ovvero configurare un nuovo certificato in modo che diventi il certificato OAuthTokenIssuer corrente in un determinato momento. Il comando seguente ad esempio recupera il certificato predefinito e quindi lo configura in modo che subentri come certificato OAuthTokenIssuer corrente a partire dal 1° luglio 2012:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

Il 1° luglio 2012 il nuovo certificato verrà configurato come certificato OAuthTokenIssuer corrente e il certificato OAuthTokenIssuer attivo fino a quel momento verrà configurato come certificato precedente.

Se non si desidera utilizzare Windows PowerShell, è possibile utilizzare la console MMC Certificati per esportare un certificato da un Front End Server e quindi importarlo in tutti gli altri Front End Server. Se si sceglie questa soluzione, esportare la chiave privata insieme al certificato.

<div>


> [!WARNING]
> In questo caso, la procedura deve essere eseguita in ogni Front End Server. Quando si esporta e si importano certificati in questo modo, Lync Server 2013 non replica il certificato in ogni Front End Server.



</div>

Dopo che il certificato è stato importato in tutti i Front End Server, tale certificato può essere assegnato tramite la distribuzione guidata di Lync Server anziché Windows PowerShell. Per assegnare un certificato utilizzando la Distribuzione guidata, eseguire le operazioni seguenti in un computer in cui è stata installata la Distribuzione guidata:

1.  Fare clic sul pulsante Start, scegliere tutti i programmi, **Microsoft Lync server 2013**e quindi **distribuzione guidata di Lync Server**.

2.  Nella Distribuzione guidata fare clic su **Installa o aggiorna il sistema Lync Server**.

3.  Nella pagina Microsoft Lync Server 2013 fare clic sul pulsante **Esegui** al di sotto del titolo **passaggio 3: richiesta, installazione o assegnazione dei certificati**. Nota: se nel computer sono stati già installati certificati, anziché il pulsante **Esegui** sarà disponibile il pulsante **Riesegui**.

4.  Nella Configurazione guidata certificati selezionare il certificato **OAuthTokenIssuer** e quindi fare clic su **Assegna certificato**.

5.  Nella pagina **Assegnazione certificato** della procedura guidata Assegnazione certificato fare clic su **Avanti**.

6.  Nella pagina **Archivio certificati** selezionare il certificato da utilizzare per l'autenticazione da server a server e quindi fare clic su **Avanti**.

7.  Nella pagina Riepilogo assegnazione certificato fare clic su **Avanti**.

8.  Nella pagina Esecuzione comandi in corso fare clic su **Fine**.

9.  Chiudere la Creazione guidata certificati e la Distribuzione guidata.

</div>

<span> </span>

</div>

</div>

</div>

