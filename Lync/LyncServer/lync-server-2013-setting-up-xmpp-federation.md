---
title: 'Lync Server 2013: configurazione della Federazione XMPP'
description: 'Lync Server 2013: configurazione della Federazione XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8a1fa15e399b0e0596a697420042b7504f8b791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555702"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Configurazione della Federazione XMPP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-03_

Per distribuire il proxy XMPP nel server perimetrale, è necessario configurare il server perimetrale per la federazione XMPP. A tale scopo, eseguire le operazioni seguenti.

<div>

## <a name="setting-up-xmpp-federation"></a>Configurazione della federazione XMPP

1.  Accedere al computer in cui è installata la Distribuzione guidata di Lync Server come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Nel Front End Server aprire la Distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna il sistema Lync Server e quindi su Installazione o rimozione componenti di Lync Server. Fare clic su Riesegui.

3.  In Installazione componenti di Lync Server fare clic su Avanti. Nella schermata di riepilogo verranno visualizzate le azioni in esecuzione. Al termine della distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su Fine per completare la distribuzione.

4.  Nel server perimetrale aprire la Distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna il sistema Lync Server e quindi su Installazione o rimozione componenti di Lync Server. Fare clic su Riesegui.

5.  In Installazione componenti di Lync Server fare clic su Avanti. Nella schermata di riepilogo verranno visualizzate le azioni in esecuzione. Al termine della distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su Fine per completare la distribuzione.

6.  Nel server perimetrale, nella Distribuzione guidata fare clic su Riesegui accanto a Passaggio 3: Richiesta, installazione o assegnazione dei certificati.
    
    <div class=" ">
    

    > [!TIP]  
    > Se si tratta della prima distribuzione del server perimetrale, verrà visualizzato il comando Esegui anziché Riesegui.

    
    </div>

7.  Nella pagina Attività certificato disponibili fare clic su Crea una nuova richiesta di certificato.

8.  Nella pagina richiesta di certificato fare clic su Certificato perimetro esterno.

9.  Nella pagina Richiesta posticipata o immediata selezionare la casella di controllo Prepara la richiesta per l'invio posticipato.

10. Nella pagina file richiesta di certificato digitare il percorso completo e il nome del file in cui deve essere salvata la richiesta (ad esempio, c: \\ CERT \_ esterni \_ Edge. cer).

11. Nella pagina Specifica modello di certificato alternativo selezionare la casella di controllo Utilizza modello di certificato alternativo per l'autorità di certificazione selezionata, per utilizzare un modello diverso dal modello Web Server predefinito.

12. Nella pagina Impostazioni nome e sicurezza eseguire le operazioni seguenti:
    
    1.  In Nome descrittivo digitare un nome visualizzato per il certificato.
    
    2.  In Lunghezza bit specificare la lunghezza in bit (di solito, l'impostazione predefinita 2048).
    
    3.  Verificare che la casella di controllo Contrassegna come esportabile la chiave di certificato privata sia selezionata.

13. Nella pagina Informazioni sull'organizzazione digitare il nome per l'organizzazione e l'unità organizzativa, ad esempio una divisione o un reparto.

14. Nella pagina Dati geografici specificare le informazioni sulla località.

15. Nella pagina Nome soggetto/Nomi soggetto alternativi verranno visualizzate le informazioni compilate automaticamente dalla procedura guidata. Se sono necessari ulteriori nomi alternativi soggetto, specificarli nei prossimi due passaggi.

16. Nella pagina Impostazione dominio SIP su nomi soggetto alternativi (San) selezionare la casella di controllo Domain per aggiungere un SIP.\<sipdomain\> voce all'elenco dei nomi alternativi del soggetto.

17. Nella pagina Configura nomi alternativi soggetto aggiuntivi specificare eventuali nomi alternativi soggetto aggiuntivi richiesti.
    
    <div class=" ">
    

    > [!TIP]  
    > Se è installato il proxy XMPP, per impostazione predefinita il nome di dominio (ad esempio contoso.com) viene compilato nelle voci SAN. Se sono necessarie ulteriori voci, aggiungerle in questo passaggio.

    
    </div>

18. Nella pagina Riepilogo richiesta esaminare le informazioni sul certificato da utilizzare per generare la richiesta.

19. Al termine dell'esecuzione dei comandi è possibile fare clic su Visualizza log o su Avanti per continuare.

20. Nella pagina File richiesta di certificato è possibile visualizzare il file di richiesta di firma del certificato (CSR) generato facendo clic su Visualizza oppure è possibile fare clic su Fine per uscire dalla Configurazione guidata certificati.

21. Copiare il file di richiesta e inviarlo all'Autorità di certificazione (CA) pubblica.

22. Dopo aver ricevuto, importato e assegnato il certificato pubblico, è necessario arrestare e riavviare i servizi del server perimetrale. A tale scopo, digitare quanto segue nella console di gestione di Lync Server:
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. Per configurare DNS per la Federazione XMPP, è necessario aggiungere il record SRV seguente al DNS esterno: \_ XMPP-server. \_ TCP.\<domain name\> Il record SRV si risolverà nell'FQDN del server perimetrale di Access Edge, con un valore di porta pari a 5269. È inoltre necessario configurare un record host 'A' (ad esempio, xmpp.contoso.com) che punta all'indirizzo IP del server Access Edge.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Se esistono pool di server perimetrali in più siti, è consigliabile aggiungere più record SRV per la federazione XMPP. Aggiungere un record SRV per ogni pool di server perimetrali nell'organizzazione e assegnare una diversa priorità a ognuno di questi record SRV. Quando tutti i pool di server perimetrali sono in esecuzione, le richieste XMPP verranno tutte gestite dal pool di server perimetrali prioritario, ma se tale pool di server perimetrali diventa inattivo sarà necessario aggiungere un nuovo record SRV per ripristinare la funzionalità di federazione XMPP.

    
    </div>

24. Configurare nuovi criteri di accesso esterno per abilitare tutti gli utenti. A tale scopo, aprire Lync Server Management Shell nel Front End Server e digitare:
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    Abilitare l'accesso XMPP per gli utenti esterni digitando:
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. Nel server perimetrale in cui è distribuito il proxy XMPP, aprire un prompt dei comandi o un'interfaccia della riga di comando di Windows PowerShell™ e digitare quanto segue:
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    Il comando **netstat –ano** è un comando per le statistiche di rete, i parametri **–ano** richiedono che il comando netstat visualizzi tutte le connessioni e le porte di attesa, che l'indirizzo e le porte vengano visualizzati in forma numerica e che l'ID del processo proprietario venga associato a ogni connessione. Il carattere **|** definisce una pipe al comando successivo, **findstr**o trova stringa. Il numero 5269 e 23456 passato a findstr come parametro indica a findstr di eseguire la ricerca nell'output di netstat per le stringhe 5269 e 23456. Se XMPP è configurato correttamente, il risultato dei comandi dovrebbe generare connessioni di attesa e stabilite, sia nelle interfacce esterne (porta 5269) sia in quelle interne (porta 23456) del server perimetrale.
    
    Se i comandi non restituiscono porte attivate o in attesa per 5269 e 23456, controllare quanto segue:

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>Risoluzione dei problemi relativi alla federazione XMPP

1.  Per stabilire se il proxy XMPP è in esecuzione, eseguire le operazioni seguenti:

2.  Accedere al server perimetrale che esegue il servizio proxy XMPP con un account membro del gruppo degli amministratori locali.

3.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Servizi**.

4.  In Servizi individuare il servizio Lync Server XMPP Translating Gateway Proxy. Questo servizio dovrebbe essere in stato **Avviato**. In caso contrario, fare clic sull'icona **Avvia** sulla barra degli strumenti. L'icona ha la forma di una freccia verde rivolta a destra.

5.  Verificare che lo stato del servizio sia diventato **Avviato**. Se l'avvio è stato completato correttamente, chiudere **Servizi** e continuare.
    
    Se il servizio non è stato avviato, da Strumenti di amministrazione aprire Visualizzatore eventi e controllare gli errori e gli avvisi nella parte **Lync Server** in **Registri applicazioni e servizi**.

6.  Quando il sevizio **Lync Server XMPP Translating Gateway** è in esecuzione, ricontrollare i comandi netstat utilizzati in precedenza. Se non si vedono sessioni consolidate o in attesa, controllare e verificare che la **Route di federazione XMPP** sia configurata correttamente in Generatore di topologie

7.  Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

8.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

9.  In Generatore di topologie selezionare il sito per la route di federazione XMPP e la revisione per confermare che l' **assegnazione della route di Federazione del sito** per la **Federazione XMPP** indichi il server perimetrale o il pool di Edge come assegnazione della route di federazione XMPP selezionata.
    
    Se l'assegnazione della route non è corretta o non è impostata, fare clic con il pulsante destro del mouse sul sito e scegliere **Modifica proprietà**. Selezionare la casella di controllo Federazione XMPP e quindi selezionare il server perimetrale o il pool di Edge corretti.

10. Pubblicare la topologia. Per ulteriori informazioni, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > Sebbene non sia richiesto e in genere non necessario, è possibile che sia necessario riavviare i server perimetrali

    
    </div>

11. Se si utilizza il processo netstat utilizzato in precedenza, verificare che il server perimetrale sia in attesa o che abbia stabilito sessioni sulla porta 5269 e sulla porta 23456.

12. Se ancora non vengono visualizzate le sessioni previste, controllare nel Visualizzatore eventi per individuare le possibili cause del problema di comunicazione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esempio di configurazione XMPP in Lync Server 2013 – Federazione XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Gestire i partner federati XMPP in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

