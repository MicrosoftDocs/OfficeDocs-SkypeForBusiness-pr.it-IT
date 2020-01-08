---
title: Assegnazione di un certificato di autenticazione server-server a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63d4e5e3ac8c544e83ab9cfb8f82a5c70f86131b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>Assegnazione di un certificato di autenticazione da server a server a Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-24_

Per determinare se un certificato di autenticazione da server a server è già stato assegnato a Microsoft Lync Server 2013, eseguire il comando seguente da Lync Server 2013 Management Shell:

    Get-CsCertificate -Type OAuthTokenIssuer

Se non vengono restituite informazioni di certificato, è necessario assegnare un certificato dell'autorità di certificazione per poter usare l'autenticazione da server a server. Come regola generale, qualsiasi certificato di Lync Server 2013 può essere usato come certificato di OAuthTokenIssuer; ad esempio, il certificato predefinito di Lync Server 2013 può essere usato anche come certificato OAuthTokenIssuer. Il certificato OAUthTokenIssuer può essere anche qualsiasi certificato del server Web che include il nome del dominio SIP nel campo oggetto. I due requisiti principali per il certificato usato per l'autenticazione da server a server sono i seguenti: 1) lo stesso certificato deve essere configurato come certificato OAuthTokenIssuer in tutti i server front-end. e 2) il certificato deve essere di almeno 2048 bit.

Se non si dispone di un certificato che può essere usato per l'autenticazione da server a server, è possibile ottenere un nuovo certificato, importare il nuovo certificato e quindi usare tale certificato per l'autenticazione da server a server. Dopo aver richiesto e ottenuto il nuovo certificato, è possibile accedere a uno dei server front-end e usare un comando di Windows PowerShell simile a quello per importare e assegnare il certificato:

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

Nel comando precedente il parametro path rappresenta il percorso completo del file di certificato e il parametro password rappresenta la password assegnata al certificato. Questa procedura deve essere eseguita una sola volta: il servizio di replica di Lync Server creerà automaticamente un set di attività pianificate che decriptano e distribuiscono il certificato in tutti i server front-end.

In alternativa, puoi usare un certificato esistente come certificato di autenticazione da server a server. Come indicato, il certificato predefinito può essere usato come certificato di autenticazione da server a server. La coppia di comandi di Windows PowerShell seguente recupera il valore della proprietà identificazione personale del certificato predefinito, quindi usa questo valore per rendere il certificato predefinito il certificato di autenticazione da server a server:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

Nel comando precedente il certificato recuperato è configurato per funzionare come certificato di autenticazione server-server globale; Ciò significa che il certificato verrà replicato e usato da tutti i server front-end. Anche in questo caso, questo comando deve essere eseguito solo una volta e solo in uno dei server front-end. Anche se tutti i server front-end devono usare lo stesso certificato, non è necessario configurare il certificato OAuthTokenIssuer in ogni server front-end. Configurare invece il certificato una sola volta, quindi consentire al server di replica di Lync Server di eseguire la copia di tale certificato in ogni server.

Il cmdlet Set-CsCertificate accetta il certificato in questione e configura immediatamente il certificato in modo che agisca come certificato OAuthTokenIssuer corrente. Lync Server 2013 mantiene due copie di un tipo di certificato: il certificato corrente e il certificato precedente. Se è necessario che il nuovo certificato cominci subito ad agire come certificato OAuthTokenIssuer, è necessario usare il cmdlet Set-CsCertificate.

Puoi anche usare il cmdlet Set-CsCertificate per "eseguire il rollback" di un nuovo certificato. "Rotolare" un certificato significa semplicemente configurare un nuovo certificato per diventare il certificato corrente di OAuthTokenIssuer in un determinato momento. Ad esempio, questo comando Recupera il certificato predefinito e quindi configura tale certificato per subentrare come certificato OAuthTokenIssuer corrente al 1 ° luglio 2012:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

Il 1 ° luglio 2012 il nuovo certificato verrà configurato come certificato OAuthTokenIssuer corrente e il certificato di OAuthTokenIssuer "vecchio" verrà configurato come certificato precedente.

Se non si vuole usare Windows PowerShell, è anche possibile usare la console MMC certificati per esportare un certificato da un server front-end e quindi importare lo stesso certificato in tutti gli altri server front-end. In questo caso, assicurati di esportare la chiave privata insieme al certificato stesso.

<div>


> [!WARNING]
> In questo caso, la procedura deve essere eseguita su ogni server front-end. Quando si esportano e si importano certificati in questo modo, Lync Server 2013 non replica tale certificato in ogni server front-end.



</div>

Dopo aver importato il certificato in tutti i server front-end, tale certificato può essere assegnato tramite la distribuzione guidata di Lync Server anziché Windows PowerShell. Per assegnare un certificato tramite la distribuzione guidata, eseguire la procedura seguente in un computer in cui è stata installata la distribuzione guidata:

1.  Fare clic sul pulsante Start, scegliere tutti i programmi, **Microsoft Lync server 2013**e quindi fare clic su **distribuzione guidata Lync Server**.

2.  Nella distribuzione guidata fare clic su **Installa o aggiorna Lync Server System**.

3.  Nella pagina Microsoft Lync Server 2013 fare clic sul pulsante **Esegui** sotto il titolo **passaggio 3: Richiedi, installa o assegna certificati**. Nota: se sono già stati installati certificati in questo computer, il pulsante **Esegui** verrà etichettato di **nuovo in esecuzione**.

4.  Nella procedura guidata certificato selezionare il certificato **OAuthTokenIssuer** e quindi fare clic su **assegna**.

5.  Nella pagina **assegnazione** certificato della procedura guidata assegnazione certificati fare clic su **Avanti**.

6.  Nella pagina **archivio certificati** selezionare il certificato da usare per l'autenticazione da server a server e quindi fare clic su **Avanti**.

7.  Nella pagina Riepilogo assegnazione certificati fare clic su **Avanti**.

8.  Nella pagina esecuzione dei comandi fare clic su **fine**.

9.  Chiudere la procedura guidata certificato e la distribuzione guidata.

</div>

<span> </span>

</div>

</div>

</div>

