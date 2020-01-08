---
title: 'Lync Server 2013: Configurazione della federazione di XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cda79f7b80d6f1bbdf2163ecf987f4a05949bfc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Configurazione della federazione di XMPP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-12-03_

Per distribuire il proxy XMPP nell'Edge Server, è necessario configurare l'Edge Server per la Federazione XMPP. A questo scopo, eseguire la procedura seguente.

<div>

## <a name="setting-up-xmpp-federation"></a>Configurazione della Federazione XMPP

1.  Accedere al computer in cui è installata la distribuzione guidata di Lync Server come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Nel server front-end aprire la distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna Lync Server System, quindi fare clic su Imposta o Rimuovi componenti di Lync Server. Fare di nuovo clic su Esegui.

3.  In configurazione componenti di Lync Server fare clic su Avanti. La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite. Dopo aver completato la distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su fine per completare la distribuzione.

4.  Nell'Edge Server aprire la distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna Lync Server System, quindi fare clic su Imposta o Rimuovi componenti di Lync Server. Fare di nuovo clic su Esegui.

5.  In configurazione componenti di Lync Server fare clic su Avanti. La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite. Dopo aver completato la distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su fine per completare la distribuzione.

6.  Nel server perimetro, nella distribuzione guidata, accanto a passaggio 3: richiedere, installare o assegnare certificati, fare di nuovo clic su Esegui.
    
    <div class=" ">
    

    > [!TIP]  
    > Se si distribuisce il server perimetrale per la prima volta, verrà visualizzato di nuovo Esegui anziché Esegui.

    
    </div>

7.  Nella pagina attività certificato disponibili fare clic su Crea una nuova richiesta di certificato.

8.  Nella pagina richiesta certificato fare clic su certificato bordo esterno.

9.  Nella pagina richiesta posticipata o immediata selezionare la casella di controllo prepara la richiesta ora, ma inviarla in seguito.

10. Nella pagina file di richiesta certificato digitare il percorso completo e il nome file del file in cui deve essere salvata la richiesta, ad esempio c:\\CERT\_exernal\_Edge. cer.

11. Nella pagina specifica modello di certificato alternativo, per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo Usa il modello di certificato alternativo per l'autorità di certificazione selezionata.

12. Nella pagina impostazioni di sicurezza e nome eseguire le operazioni seguenti:
    
    1.  In nome descrittivo digitare un nome visualizzato per il certificato
    
    2.  In bit length specificare la lunghezza in bit (in genere, il valore predefinito di 2048)
    
    3.  Verificare che la casella di controllo contrassegna la chiave privata del certificato come esportabile sia selezionata

13. Nella pagina informazioni organizzazione digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio divisione o reparto.

14. Nella pagina informazioni geografiche specificare le informazioni sulla posizione

15. Nella pagina nome oggetto/nomi oggetto alternativo vengono visualizzate le informazioni che verranno inserite automaticamente dalla procedura guidata. Se sono necessari altri nomi alternativi per l'oggetto, è necessario specificarli nei due passaggi successivi

16. Nell'impostazione del dominio SIP nella pagina nome alternativo oggetto (SANs) selezionare la casella di controllo Domain per aggiungere un SIP. \<SipDomain\> voce nell'elenco nomi alternativi oggetto.

17. Nella pagina Configura altri nomi alternativi oggetto specificare eventuali altri nomi alternativi per gli argomenti necessari
    
    <div class=" ">
    

    > [!TIP]  
    > Se il proxy XMPP è installato, per impostazione predefinita il nome di dominio, ad esempio contoso.com, viene popolato nelle voci SAN. Se sono necessarie altre voci, aggiungerle in questo passaggio.

    
    </div>

18. Nella pagina Riepilogo richieste verificare le informazioni sul certificato da usare per generare la richiesta.

19. Dopo che i comandi hanno terminato l'uso, è possibile visualizzare il log oppure fare clic su Avanti per continuare.

20. Nella pagina file di richiesta di certificato è possibile visualizzare il file della richiesta di firma del certificato (CSR) generato facendo clic su Visualizza o Esci dalla creazione guidata certificato facendo clic su fine.

21. Copiare il file di richiesta e inviarlo all'autorità di certificazione pubblica.

22. Dopo la ricezione, l'importazione e l'assegnazione del certificato pubblico, è necessario arrestare e riavviare i servizi Edge Server. A tale scopo, digitare la console di gestione di Lync Server:
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

23. Per configurare il DNS per la Federazione XMPP, è possibile aggiungere il record SRV seguente al\_DNS esterno: XMPP-server. \_TCP. \<nome\> di dominio il record SRV verrà risolto nell'FQDN di Access Edge del server Edge, con un valore di porta 5269. Inoltre, configuri un record host "A" (ad esempio xmpp.contoso.com) che punta all'indirizzo IP di Access Edge Server.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Se si hanno pool di bordi in più siti, è consigliabile aggiungere più record SRV per la Federazione XMPP. Aggiungere un record SRV per ogni pool di Edge nell'organizzazione e assegnare a ognuno di questi record SRV una priorità diversa. Quando tutti i pool di bordi sono in esecuzione, le richieste XMPP verranno gestite dal pool di Edge con la prima priorità, ma se tale pool di Edge scende, non dovrai aggiungere un nuovo record SRV per recuperare le funzionalità federative XMPP.

    
    </div>

24. Configurare un nuovo criterio di accesso esterno per abilitare tutti gli utenti aprendo Lync Server Management Shell sul front-end e digitando:
    
       ```
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    Abilitare l'accesso XMPP per gli utenti esterni digitando:
    
       ```
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. Nell'Edge Server in cui è distribuito il proxy XMPP aprire un prompt dei comandi o un'interfaccia della riga di comando™ di Windows PowerShell e digitare quanto segue:
    
       ```
        Netstat -ano | findstr 5269
       ```
    
       ```
        Netstat -ano | findstr 23456
       ```
    
    Il comando **netstat-ano** è un comando di statistiche di rete, i parametri **-richiesta ano** che netstat Visualizza tutte le connessioni e le porte in ascolto, l'indirizzo e le porte vengono visualizzati in forma numerica e l'ID processo proprietario è associato a ogni connessione. Il carattere **|** definisce una pipe per il comando successivo, **findstr**o trova stringa. Il numero 5269 e 23456 passato a findstr come parametro indica a findstr di cercare l'output di netstat per le stringhe 5269 e 23456. Se XMPP è configurato correttamente, il risultato dei comandi deve comportare connessioni in ascolto e stabilite, sia nelle interfacce esterne (porta 5269) che in quelle interne (porta 23456) del server perimetrale.
    
    Se i comandi non restituiscono porte stabilite o in ascolto in 5269 e 23456, eseguire le operazioni seguenti:

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>Risoluzione dei problemi relativi alla Federazione XMPP

1.  Per determinare se il proxy XMPP è in uso, eseguire le operazioni seguenti:

2.  Accedere all'Edge Server che sta usando il servizio proxy XMPP come membro del gruppo dell'amministratore locale.

3.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi **Servizi**

4.  In servizi individuare il proxy del gateway di traduzione XMPP di Lync Server. Il servizio deve essere nello stato **Started** . Se non è stata avviata, fare clic sull'icona **Start** sulla barra degli strumenti. L'icona viene visualizzata come freccia verde e rivolta verso destra.

5.  Verificare che il servizio sia stato modificato in **iniziato**. Se è stata avviata correttamente, chiudere i **Servizi** e continuare.
    
    Se il servizio non è stato avviato correttamente, da strumenti di amministrazione aprire il Visualizzatore eventi e fare riferimento agli errori e agli avvisi presenti nella parte **Lync Server** in **registri applicazioni e servizi**.

6.  Una volta che il servizio **gateway di traduzione XMPP di Lync Server** è in uso, ripetere il controllo dei comandi netstat usati in precedenza. Se non si vedono sessioni consolidate o in ascolto, verificare e verificare che la **Route federativo XMPP** sia configurata correttamente in Generatore di topologie

7.  Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

8.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

9.  In Generatore di topologie selezionare il sito per la route della Federazione XMPP e la revisione per verificare che l' **assegnazione della route Federation del sito** per la **Federazione XMPP** indichi il server perimetrale o il pool di Edge come assegnazione della route Federation XMPP selezionata.
    
    Se l'assegnazione della route non è corretta o non è impostata, fare clic con il pulsante destro del mouse sul sito, scegliere **modifica proprietà**. Selezionare la casella di controllo Federazione XMPP e quindi selezionare il server Edge o il pool di Edge corretto.

10. Pubblicare la topologia. Per informazioni dettagliate, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > Sebbene non sia richiesto e in genere non necessario, è possibile che sia necessario riavviare gli Edge Server

    
    </div>

11. Usando il processo netstat usato in precedenza, verificare che il server perimetrale sia ora in ascolto o abbia stabilito sessioni sulla porta 5269 e la porta 23456.

12. Se non si vedono ancora le sessioni previste, controllare il Visualizzatore eventi per eventuali cause di contributo per il problema di comunicazione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esempio di configurazione XMPP in Lync Server 2013 - federazione di XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Gestire i partner federati XMPP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

