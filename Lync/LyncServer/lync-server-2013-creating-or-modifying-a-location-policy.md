---
title: 'Lync Server 2013: creazione o modifica di un criterio percorso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60196805cccc13c35d4a4db1aa2ea7ac8e6a9fef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Creazione o modifica di un criterio percorso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

In Lync Server 2013, è possibile utilizzare i criteri percorso per applicare le impostazioni relative alla funzionalità Enhanced 9-1-1 (E9-1-1) e alle impostazioni di posizione per utenti o contatti. I criteri di posizione determinano se un utente è abilitato per E9-1-1 e in questo caso il funzionamento di una chiamata di emergenza. Ad esempio, è possibile usare i criteri di posizione per definire il numero di emergenza (ad esempio il 113 in Italia), se la sicurezza aziendale deve essere automaticamente notificata e come instradare la chiamata.

È possibile configurare i criteri percorso dal gruppo **configurazione di rete** nel pannello di controllo di Lync Server 2013. Dal pannello di controllo di Lync Server è possibile visualizzare, creare, modificare o eliminare i criteri di percorso. Utilizzare le procedure descritte in questa sezione per creare o modificare un criterio percorso. Per informazioni dettagliate sull'eliminazione dei criteri percorso, vedere [eliminazione di un criterio percorso in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).

In Lync Server 2013, è possibile ignorare il periodo di tempo predefinito tra le richieste dei client per un aggiornamento del percorso dal servizio informazioni percorso. Il valore predefinito è 4 ore. Per ignorare il valore predefinito, utilizzare il cmdlet **Set-CsLocationPolicy** con il parametro LocationRefreshInterval.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>Per creare un nuovo criterio percorso nel pannello di controllo di Lync Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su  **Configurazione di rete ** e quindi su  **Criteri percorso **.

4.  Nella pagina **Criteri percorso** fare clic su **Nuovo** e quindi selezionare il tipo di criterio che si desidera creare:
    
      - Per creare un criterio sito, fare clic su **Criteri sito**. In **Seleziona un sito** selezionare il sito a cui si desidera applicare il criterio e fare clic su **OK**. Nella pagina **Crea nuovi criteri percorso** il campo **Ambito** conterrà il valore **Sito**, mentre il campo **Nome** conterrà il nome del sito selezionato. Tali campi non possono essere modificati. Un criterio sito viene infatti applicato automaticamente a tutti gli utenti del sito specificato e ha la priorità sul criterio globale valido per tali utenti.
    
      - Per creare un** **criterio utente, fare clic su **Criteri utente**. Nella pagina **Crea nuovi criteri percorso** il campo **Ambito** conterrà il valore **Utente**. Tale valore non può essere modificato. Nel campo **Nome** digitare il nome che si desidera assegnare al criterio. Un criterio utente non viene applicato automaticamente a qualsiasi utente. Dopo avere creato tale criterio, è necessario assegnarlo manualmente agli utenti o ai siti di rete a cui si desidera applicarlo.

5.  Completare i campi restanti come indicato di seguito:
    
      - **Abilita servizi di emergenza avanzati**   Selezionare questa casella di controllo per abilitare gli utenti associati a questo criterio per il servizio E9-1-1. Quando i servizi di emergenza sono abilitati, i client di Lync Server recupereranno le informazioni sulla posizione sulla registrazione e includeranno tali informazioni quando viene effettuata una chiamata di emergenza.
    
      - **Percorso**   specificare uno dei seguenti valori:
        
          - **Obbligatorio**   all'utente verrà richiesto di immettere le informazioni sulla posizione quando il client si registra in una nuova posizione. L'utente può ignorare la richiesta e non immettere alcuna informazione. Se le informazioni vengono immesse, alla chiamata di emergenza effettuata risponderà innanzitutto il provider dei servizi di emergenza per verificare la posizione prima dell'instradamento al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point).
        
          - **Non è necessario**   che all'utente non venga richiesto un percorso. Quando viene effettuata una chiamata senza informazioni sulla posizione, il provider dei servizi di emergenza risponderà alla chiamata e richiederà la posizione.
        
          - **Dichiarazione**   di non responsabilità questa opzione è identica a quella **richiesta** , tranne per il fatto che l'utente non può ignorare la richiesta senza immettere le informazioni sulla posizione. L'utente può comunque effettuare una chiamata di emergenza, ma non è possibile effettuare altre chiamate senza immettere le informazioni. Viene inoltre visualizzato il testo della dichiarazione di non responsabilità per comunicare all'utente le conseguenze derivanti dal rifiuto di immettere le informazioni sulla posizione. Per impostare il testo della dichiarazione di non responsabilità, è necessario utilizzare Lync Server Management Shell per eseguire il cmdlet **Set-CsLocationPolicy** o il cmdlet **New-CsLocationPolicy** con il parametro EnhancedEmergencyServiceDisclaimer. Per informazioni dettagliate, vedere [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) o [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) nella documentazione di Lync Server Management Shell.
            
            <div>
            

            > [!NOTE]  
            > In Lync Server 2013, è possibile utilizzare i criteri percorso per impostare diverse dichiarazioni di non responsabilità per le diverse impostazioni locali o diversi gruppi di utenti, a differenza di Lync Server 2010, in cui è possibile specificare solo una dichiarazione di rinunce globale per l'intera organizzazione.

            
            </div>
    
      - **Utilizzo del percorso per i servizi di emergenza solo**   Lync può utilizzare le informazioni sulla posizione per diversi motivi, ad esempio per informare i compagni di squadra del percorso corrente. Selezionare questa casella di controllo per verificare che le informazioni sulla posizione siano disponibili solo per l'utilizzo con una chiamata di emergenza.
    
      - **Utilizzo PSTN l'**   utilizzo della rete PSTN (Public Switched Telephone Network) che verrà utilizzato per determinare la route vocale utilizzata per instradare le chiamate di emergenza provenienti dai client che utilizzano questo profilo. La route associata a tale utilizzo deve puntare a un trunk SIP dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al punto di raccolta PSAP più vicino.
    
      - **Numero di chiamata di emergenza**   il numero che viene composto per raggiungere i servizi di emergenza. In Italia il numero è "112". La stringa deve essere costituita da cifre comprese tra 0 e 9 con una lunghezza massima di 10 cifre.
    
      - **Maschera di chiamata di emergenza**   numero che si desidera tradurre nel valore del valore del numero di composizione di emergenza quando viene composto. Ad esempio, se si immette il valore 212 in questo campo e il campo numero di composizione di emergenza ha un valore pari a 911, se un utente compone 212, la chiamata verrà effettuata a 911. In questo modo è possibile comporre numeri di emergenza alternativi e continuare a chiamare i servizi di emergenza REACH (ad esempio, se un utente di un paese o un'area geografica con un numero di emergenza diverso cerca di comporre il numero del paese o dell'area geografica anziché il numero del paese o area geografica in cui si trovano attualmente. È possibile definire più maschere di composizione del numero di emergenza separando i valori con un punto e virgola. Ad esempio, 212; 414. La lunghezza massima della stringa è 100 caratteri. Ogni carattere deve essere costituito da una cifra compresa tra 0 e 9.
        
        <div>
        

        > [!IMPORTANT]  
        > Accertarsi che il valore specificato come maschera di composizione non corrisponda a un numero dell'intervallo di codici orbit del parcheggio di chiamata. L'instradamento del parcheggio di chiamata avrà infatti la precedenza sulla conversione delle stringhe di composizione per le chiamate di emergenza. Per visualizzare gli intervalli di codici orbit del parcheggio di chiamata esistenti, fare clic su <STRONG>Funzionalità vocali</STRONG> nella barra di spostamento sinistra e quindi fare clic su <STRONG>Parcheggio di chiamata</STRONG>. Per ulteriori informazioni, vedere <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">configurare le estensioni dei numeri di telefono per il parcheggio delle chiamate in Lync Server 2013</A>.

        
        </div>
    
      - **URI di notifica**   uno o più URI (Uniform Resource Identifier) SIP per ricevere una notifica quando viene effettuata una chiamata di emergenza. Ad esempio, l'ufficio che si occupa della sicurezza aziendale potrebbe ricevere una notifica tramite messaggio istantaneo ogni volta che viene effettuata una chiamata di emergenza. Se la posizione del chiamante è disponibile, verrà inclusa nella notifica. È possibile includere più URI SIP come elenco separato da virgole. Ad esempio, "SIP: security@litwareinc. com", "SIP: kmyer@litwareinc. com". Sono supportate le liste di distribuzione. La stringa deve avere una lunghezza da 1 a 256 caratteri e deve iniziare con il prefisso "SIP:". Prima di fare clic nel campo URI di notifica viene visualizzato un esempio.
    
      - **URI conferenza l'**   URI SIP, in questo caso il numero di telefono, di una terza parte che verrà contrattata in tutte le chiamate di emergenza effettuate. Ad esempio, l'ufficio che si occupa della sicurezza aziendale potrebbe ricevere una chiamata quando viene effettuata una chiamata di emergenza e ascoltare o partecipare alla chiamata (in base al valore specificato nel campo **Modalità conferenza**). La stringa deve avere una lunghezza compresa tra 1 e 256 caratteri e deve iniziare con il prefisso sip:. Finché non si fa clic in questo campo, viene visualizzato un esempio.
    
      - **Modalità**   conferenza se si specifica un valore nel campo **URI conferenza** , la **modalità conferenza** determina se una terza parte può partecipare alla chiamata o può solo essere ascoltata. Selezionare una delle opzioni seguenti:
        
          - **Una terza**parte può solo ascoltare la conversazione tra il chiamante e l'operatore di PSAP.   
        
          - ****   È possibile che una terza parte sia in ascolto e partecipi alla chiamata tra il chiamante e l'operatore di PSAP.

6.  Fare clic su **Commit**.
    
    <div>
    

    > [!IMPORTANT]  
    > Quando si crea un criterio utente, inizialmente tale criterio non viene applicato ad alcun utente o sito di rete. Per applicare il criterio a un utente, fare clic su <STRONG>Utenti</STRONG> sulla barra di spostamento sinistra, individuare l'utente a cui applicare il criterio, scegliere <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>Modifica</STRONG> e nella pagina <STRONG>Modifica utente di Lync Server</STRONG> selezionare il nuovo criterio percorso nell'elenco a discesa <STRONG>Criteri percorso</STRONG>, quindi fare clic su <STRONG>Commit</STRONG>.<BR>Per applicare il criterio a un sito di rete, fare clic su <STRONG>Configurazione di rete</STRONG> sulla barra di spostamento sinistra, fare clic su <STRONG>Sito</STRONG>, individuare il sito di rete a cui applicare il criterio, scegliere <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>Modifica</STRONG> e in <STRONG>Modifica sito</STRONG> selezionare il nuovo criterio percorso nell'elenco a discesa <STRONG>Criteri percorso</STRONG>, quindi fare clic su <STRONG>Commit</STRONG>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>Per modificare un criterio percorso nel pannello di controllo di Lync Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri percorso**.

4.  Nella pagina **Criteri percorso** selezionare il criterio percorso che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **Modifica criteri percorso** modificare i campi in base alle proprie esigenze. Per informazioni dettagliate, vedere il passaggio 5 nelle procedure "Per creare un nuovo criterio percorso" più indietro in questo argomento.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminazione di un criterio percorso in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md)  


[Definizione dei criteri percorso per Lync Server 2013](lync-server-2013-defining-the-location-policy.md)  


[Configurare le estensioni dei numeri di telefono per il parcheggio delle chiamate in Lync Server 2013](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

