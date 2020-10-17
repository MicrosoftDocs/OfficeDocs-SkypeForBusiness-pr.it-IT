---
title: 'Lync Server 2013: creare impostazioni di configurazione del servizio di registrazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2baa4cd40ae0f6421dbb01facecf0ab41825fc31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501593"
---
# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Creare le impostazioni di configurazione di registrazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-17_

È possibile utilizzare la funzione di registrazione per configurare metodi di autenticazione di server proxy. Il protocollo di autenticazione specificato determina il tipo di richieste dei server del pool per i client. I protocolli disponibili sono i seguenti:

  - **Kerberos**     Questo è il più potente schema di autenticazione basato su password disponibile per i client, ma è in genere disponibile solo per i client aziendali, poiché richiede la connessione client a un centro distribuzione chiavi (controller di dominio Kerberos). Questa impostazione è appropriata se il server deve eseguire solo l'autenticazione dei client aziendali.

  - **NTLM**     Questa è l'autenticazione basata su password disponibile per i client che utilizzano uno schema di hashing Challenge-Response sulla password. È l'unica forma di autenticazione disponibile per i client senza connettività a un Centro distribuzione chiavi (controller di dominio Kerberos), ad esempio gli utenti remoti. Se un server autentica solo utenti remoti, è consigliabile scegliere NTLM.

  - **Autenticazione**     del certificato Si tratta del nuovo metodo di autenticazione quando il server deve ottenere i certificati da client Lync Phone Edition, telefoni delle aree comuni, Lync 2013 e l'app Lync Windows Store. Nei client di Lync Phone Edition, dopo che un utente ha eseguito l'accesso ed è stato autenticato fornendo un PIN (Personal Identification Number), Lync Server 2013 quindi accantona l'URI SIP sul telefono e fornisce un certificato firmato Lync Server o un certificato utente che identifica Joe (ex: SN=joe@contoso.com) nel telefono. Questo certificato viene utilizzato per l'autenticazione con la funzione di Registrazione avanzata e i servizi Web.

<div>


> [!NOTE]  
> È consigliabile abilitare sia Kerberos sia NTLM quando un server supporta l'autenticazione per client remoti e aziendali. Il server perimetrale e i server interni comunicano per assicurare che ai client remoti venga offerta solo l'autenticazione NTLM. I server in cui è abilitata solo l'autenticazione Kerberos non sono in grado di autenticare gli utenti remoti. Se il server autentica anche gli utenti aziendali, viene utilizzato Kerberos.<BR>Se si utilizzeranno i client app di Windows Store di Lync, è necessario abilitare l'autenticazione dei certificati.



</div>

Eseguire la procedura seguente per creare una nuova funzione di registrazione.

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>Per creare nuove impostazioni di configurazione del servizio di registrazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Sicurezza**, quindi su **Funzione di registrazione**.

4.  Nella pagina **Funzione di registrazione** fare clic su **Nuovo**

5.  In **Seleziona un servizio** fare clic sul servizio a cui applicare la funzione di registrazione e quindi su **OK**.

6.  In **Impostazione funzione di registrazione** selezionare una o più opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:
    
      - **Abilita autenticazione Kerberos** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione Kerberos.
    
      - **Abilita autenticazione NTLM** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione NTLM.
    
      - **Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.

7.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

