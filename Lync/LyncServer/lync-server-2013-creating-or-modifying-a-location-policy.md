---
title: 'Lync Server 2013: creazione o modifica di un criterio di posizione'
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
ms.openlocfilehash: 1648e845fc3759e7083c2443013f89fb49c1b00f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Creazione o modifica di un criterio di posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

In Lync Server 2013 è possibile usare i criteri di posizione per applicare le impostazioni relative alle funzionalità avanzate di 9-1-1 (E9-1-1) e alle impostazioni della posizione per gli utenti o i contatti. I criteri di posizione determinano se un utente è abilitato per E9-1-1 e, in caso affermativo, qual è il comportamento di una chiamata di emergenza. Ad esempio, è possibile usare i criteri di posizione per definire il numero che costituisce una chiamata di emergenza, ad esempio 911 negli Stati Uniti, se la sicurezza aziendale deve essere notificata automaticamente e come deve essere instradata la chiamata.

È possibile configurare i criteri di posizione dal gruppo **configurazione di rete** nel pannello di controllo di Lync Server 2013. Dal pannello di controllo di Lync Server è possibile visualizzare, creare, modificare o eliminare i criteri di posizione. Usare le procedure descritte in questa sezione per creare o modificare un criterio di posizione. Per informazioni dettagliate sull'eliminazione dei criteri di posizione, vedere [eliminazione di un criterio di posizione in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).

In Lync Server 2013 è possibile ignorare la quantità di tempo predefinita tra le richieste client per un aggiornamento della posizione dal servizio informazioni sulla posizione. Il valore predefinito è 4 ore. Usa il cmdlet **Set-CsLocationPolicy** con il parametro LocationRefreshInterval per eseguire l'override del valore predefinito.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>Per creare un nuovo criterio di posizione nel pannello di controllo di Lync Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri posizione**.

4.  Nella pagina **criteri di posizione** fare clic su **nuovo** e quindi selezionare il tipo di criterio da creare:
    
      - Per creare un criterio sito, fare clic su **criteri sito**. In **Seleziona un sito**scegliere il sito a cui si vuole applicare il criterio e fare clic su **OK**. Nella pagina **nuovo criterio di posizione** il campo **ambito** contiene il **sito**valore e il campo **nome** contiene il nome del sito scelto. Non è possibile modificare uno di questi campi. Un criterio di sito viene applicato automaticamente a tutti gli utenti nel sito specificato ed esegue l'override dei criteri globali per tali utenti.
    
      - Per creare un **criterio utente**, fare clic su **criteri utente**. Nei **nuovi criteri di posizione**il campo **ambito** contiene il valore **User**. Non è possibile modificare questo valore. Nel campo **nome** Digitare il nome che si vuole assegnare a questo criterio. Un criterio utente non si applica automaticamente agli utenti. Dopo aver creato il criterio utente, è necessario concedere manualmente il criterio agli utenti o ai siti di rete a cui si vuole applicare il criterio.

5.  Compilare i campi rimanenti come indicato di seguito:
    
      - **Abilita servizi di emergenza avanzati**   Selezionare questa casella di controllo per abilitare gli utenti associati al criterio per il servizio E9-1-1. Quando i servizi di emergenza sono abilitati, i client di Lync Server recupereranno le informazioni sulla posizione sulla registrazione e includeranno tali informazioni quando viene effettuata una chiamata di emergenza.
    
      - **Posizione**   specifica uno dei valori seguenti:
        
          - **Obbligatorio**   l'utente verrà richiesto di immettere le informazioni sulla posizione quando il client viene registrato in una nuova posizione. L'utente può chiudere la richiesta senza immettere le informazioni. Se vengono immesse informazioni, una chiamata di emergenza verrà prima di tutto risolta dal provider di servizi di emergenza per verificare la posizione prima di essere instradata all'operatore PSAP (Public Safety Answering Point), ovvero l'operatore di 911.
        
          - **Non è necessario**   che l'utente non venga richiesto per una posizione. Quando si effettua una chiamata senza informazioni sulla posizione, il provider di servizi di emergenza risponderà alla chiamata e richiederà una posizione.
        
          - **Dichiarazione**   di non responsabilità questa opzione è la stessa **richiesta** , ad eccezione del fatto che l'utente non può chiudere la richiesta senza immettere le informazioni sulla posizione. L'utente può comunque completare una chiamata di emergenza, ma non possono essere completate altre chiamate senza immettere le informazioni. Inoltre, il testo della dichiarazione di non responsabilità verrà visualizzato all'utente che può avvisare le conseguenze della diminuzione per immettere le informazioni sulla posizione. Per impostare il testo della dichiarazione di non responsabilità, è necessario usare Lync Server Management Shell per eseguire il cmdlet **Set-CsLocationPolicy** o il cmdlet **New-CsLocationPolicy** con il parametro EnhancedEmergencyServiceDisclaimer. Per informazioni dettagliate, vedere [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) o [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) nella documentazione di Lync Server Management Shell.
            
            <div>
            

            > [!NOTE]  
            > In Lync Server 2013 è possibile usare i criteri di posizione per impostare dichiarazioni di non responsabilità diverse per le diverse impostazioni locali o per diversi set di utenti, a differenza di Lync Server 2010, in cui è possibile specificare solo un Disclaimer globale per l'intera organizzazione.

            
            </div>
    
      - **Usare la posizione per i servizi di emergenza solo**   Lync può usare le informazioni sulla posizione per diversi motivi, ad esempio per segnalare ai membri del team la posizione corrente. Selezionare questa casella di controllo per assicurarsi che le informazioni sulla posizione siano disponibili solo per l'uso con una chiamata di emergenza.
    
      - **Uso PSTN l'**   utilizzo PSTN (Public Switched Telephone Network) che verrà usato per determinare quale route vocale verrà usata per instradare chiamate di emergenza da client che usano questo profilo. La route associata a tale utilizzo deve puntare a un trunk SIP dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) più vicino.
    
      - **Numero di telefono di emergenza**   il numero composto per raggiungere i servizi di emergenza. Negli Stati Uniti questo valore è 911. La stringa deve essere composta dalle cifre da 0 a 9 e può essere di lunghezza da 1 a 10 cifre.
    
      - **Maschera di emergenza digitare**   un numero che si vuole tradurre nel valore del valore del numero di telefono di emergenza quando viene composto. Ad esempio, se si immette un valore di 212 in questo campo e il campo numero di chiamata di emergenza ha un valore di 911, se un utente compone 212 la chiamata verrà eseguita a 911. In questo modo, i numeri di emergenza alternativi devono essere composti e i servizi di emergenza REACH (ad esempio, se qualcuno di un paese o di un'area geografica con un numero di emergenza diverso cerca di chiamare il numero del paese o dell'area geografica invece del numero paese o area geografica in cui si trovano attualmente. Puoi definire più maschere di chiamate di emergenza separando i valori con punti e virgola. Ad esempio, 212; 414. La lunghezza massima della stringa è di 100 caratteri. Ogni carattere deve essere una cifra da 0 a 9.
        
        <div>
        

        > [!IMPORTANT]  
        > Verificare che il valore della maschera di chiamata specificata non sia uguale a un numero in un intervallo di orbit del parcheggio delle chiamate. Il routing di Call Park avrà la precedenza sulla conversione delle stringhe di chiamata di emergenza. Per visualizzare gli intervalli di Orbit di Call Park esistenti, fare clic su <STRONG>funzionalità vocali</STRONG> nella barra di spostamento sinistra e quindi su <STRONG>Call Park</STRONG>. Per informazioni dettagliate, vedere <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">configurare le estensioni dei numeri di telefono per le chiamate di parcheggio in Lync Server 2013</A>.

        
        </div>
    
      - **URI di notifica**   uno o più identificatori URI (Uniform Resource Identifier) SIP per ricevere una notifica quando viene effettuata una chiamata di emergenza. Ad esempio, l'ufficio sicurezza aziendale può essere avvisato tramite un messaggio istantaneo ogni volta che viene effettuata una chiamata di emergenza. Se la posizione del chiamante è disponibile, tale posizione verrà inclusa nella notifica. Più URI SIP possono essere inclusi come elenco delimitato da virgole. Ad esempio, "SIP: security@litwareinc. com", "SIP: kmyer@litwareinc. com". Le liste di distribuzione sono supportate. La stringa deve essere da 1 a 256 caratteri di lunghezza e deve iniziare con il prefisso "SIP:". Prima di fare clic nel campo URI di notifica viene visualizzato un esempio.
    
      - **URI conferenza l'**   URI SIP, in questo caso il numero di telefono, di una terza persona che verrà convocata per le chiamate di emergenza effettuate. Ad esempio, l'ufficio sicurezza aziendale può ricevere una chiamata quando viene effettuata una chiamata di emergenza e ascoltare o partecipare a tale chiamata (a seconda del valore fornito nel campo **modalità conferenza** ). La stringa deve avere una lunghezza compresa tra 1 e 256 caratteri e deve iniziare con il prefisso sip:. Viene visualizzato un esempio finché non si fa clic all'interno di questo campo.
    
      - **Modalità**   conferenza se si specifica un valore nel campo **URI conferenza** , la **modalità conferenza** determina se una terza parte può partecipare alla chiamata o può solo ascoltare. Specificare una delle opzioni seguenti:
        
          - **La sola modalità**   di una terza parte può essere ascoltata solo dalla conversazione tra il chiamante e l'operatore PSAP.
        
          - **A due vie**   una terza parte può ascoltare e partecipare alla chiamata tra il chiamante e l'operatore PSAP.

6.  Fare clic su **Commit**.
    
    <div>
    

    > [!IMPORTANT]  
    > Quando si crea un criterio utente, inizialmente i criteri non si applicano a utenti o siti di rete. Per applicare il criterio a un utente, fare clic su <STRONG>utenti</STRONG> nella barra di spostamento sinistra. Individuare l'utente a cui si vuole applicare il criterio. Nel menu <STRONG>modifica</STRONG> fare clic su <STRONG>Mostra dettagli</STRONG>. Nella pagina <STRONG>modifica utente di Lync Server</STRONG> selezionare i nuovi criteri di posizione dall'elenco a discesa <STRONG>criteri di posizione</STRONG> e quindi fare clic su <STRONG>conferma</STRONG>.<BR>Per applicare il criterio a un sito di rete, fare clic su <STRONG>configurazione di rete</STRONG> nella barra di spostamento sinistra e quindi fare clic su <STRONG>sito</STRONG>. Individuare il sito di rete a cui si vuole applicare il criterio. Nel menu <STRONG>modifica</STRONG> fare clic su <STRONG>Mostra dettagli</STRONG>. In <STRONG>modifica sito</STRONG>selezionare i nuovi criteri di posizione dall'elenco a discesa <STRONG>criteri di posizione</STRONG> e quindi fare clic su <STRONG>commit</STRONG>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>Per modificare un criterio di posizione nel pannello di controllo di Lync Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri posizione**.

4.  Nella pagina **criteri di posizione** selezionare i criteri di posizione che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **modifica criterio di posizione** modificare i campi in modo necessario (per informazioni dettagliate, vedere il passaggio 5 nella sezione "per creare un nuovo criterio di posizione" in precedenza in questo argomento).

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminazione di un criterio di posizione in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md)  


[Definizione dei criteri di posizione per Lync Server 2013](lync-server-2013-defining-the-location-policy.md)  


[Configurare le estensioni dei numeri di telefono per le chiamate di parcheggio in Lync Server 2013](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

