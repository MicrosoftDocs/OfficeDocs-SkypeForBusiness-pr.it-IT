---
title: Gestire 9-1-1 avanzato e il servizio di posizione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server supporta chiamate enhanced 9-1-1 (E9-1-1) da Skype for Business client. Quando si configura Skype for Business Server per E9-1-1, le chiamate di emergenza effettuate da Skype for Business includono informazioni sulla posizione di risposta di emergenza (ERL) dal database del servizio informazioni sulla posizione.
ms.openlocfilehash: 03fee1a411b88e51f0b994de7bba65ba3f2d3edfecb14d004e6a7f98842002ab
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297282"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Gestire 9-1-1 avanzato e il servizio di posizione in Skype per Busines Server

Skype for Business Server supporta chiamate enhanced 9-1-1 (E9-1-1) da Skype for Business client. Quando si configura Skype for Business Server per E9-1-1, le chiamate di emergenza effettuate da Skype for Business includono informazioni sulla posizione di risposta di emergenza (ERL) dal database del servizio informazioni sulla posizione. Utilizzare le procedure descritte in questo articolo per gestire i criteri percorso.

> [!Note]
> Per informazioni dettagliate sulla distribuzione di funzionalità VoIP aziendale avanzate, ad esempio E9-1-1 e il servizio Informazioni percorso, vedere [Deploy advanced VoIP aziendale features](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

In Skype for Business Server, è possibile utilizzare i criteri percorso per applicare le impostazioni relative alla funzionalità Enhanced 9-1-1 (E9-1-1) e alle impostazioni di posizione per utenti o contatti. I criteri di posizione determinano se un utente è abilitato per E9-1-1 e in questo caso il funzionamento di una chiamata di emergenza. Ad esempio, è possibile usare i criteri di posizione per definire il numero di emergenza (ad esempio il 113 in Italia), se la sicurezza aziendale deve essere automaticamente notificata e come instradare la chiamata.

È possibile configurare i criteri percorso dal **gruppo Configurazione di** rete nel Pannello Skype for Business Server controllo. Dal Pannello Skype for Business Server controllo è possibile visualizzare, creare, modificare o eliminare i criteri percorso. Utilizzare la seguente procedura per visualizzare informazioni sui criteri percorso. 


## <a name="view-location-policy-information"></a>Visualizzare le informazioni sui criteri percorso 

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Criteri **percorso.**

4.  Nella pagina **Criteri percorso** selezionare il criterio percorso che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.
 
    > [!NOTE]  
    > È possibile visualizzare le informazioni su un solo criterio percorso alla volta.

Per impostazione predefinita, esiste un solo criterio, denominato Globale, e non può essere eliminato o rinominato. È tuttavia possibile modificarlo. Tale criterio verrà applicato a tutti gli utenti e i contatti, a meno che non vengano creati criteri sito o criteri utente. I criteri utente devono essere applicati a utenti specifici.


## <a name="create-or-modify-a-location-policy"></a>Creare o modificare un criterio percorso 

In Skype for Business Server, è possibile ignorare la quantità di tempo predefinita tra le richieste dei client per un aggiornamento della posizione dal servizio informazioni sulla posizione. Il valore predefinito è 4 ore. Per ignorare il valore predefinito, utilizzare il cmdlet **Set-CsLocationPolicy** con il parametro LocationRefreshInterval.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Per creare un nuovo criterio percorso nel Pannello Skype for Business Server di controllo

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Criteri **percorso.**

4.  Nella pagina **Criteri percorso** fare clic su **Nuovo** e quindi selezionare il tipo di criterio che si desidera creare:
    
      - Per creare un criterio sito, fare clic su **Criteri sito**. In **Seleziona un sito** selezionare il sito a cui si desidera applicare il criterio e fare clic su **OK**. Nella pagina **Crea nuovi criteri percorso** il campo **Ambito** conterrà il valore **Sito**, mentre il campo **Nome** conterrà il nome del sito selezionato. Tali campi non possono essere modificati. Un criterio sito viene infatti applicato automaticamente a tutti gli utenti del sito specificato e ha la priorità sul criterio globale valido per tali utenti.
    
      - Per creare un **** criterio utente, fare clic su **Criteri utente**. Nella pagina **Crea nuovi criteri percorso** il campo **Ambito** conterrà il valore **Utente**. Tale valore non può essere modificato. Nel campo **Nome** digitare il nome che si desidera assegnare al criterio. Un criterio utente non viene applicato automaticamente a qualsiasi utente. Dopo avere creato tale criterio, è necessario assegnarlo manualmente agli utenti o ai siti di rete a cui si desidera applicarlo.

5.  Completare i campi restanti come indicato di seguito:
    
      - **Abilitare servizi di emergenza avanzato**   Selezionare questa casella di controllo per abilitare gli utenti associati a questo criterio per E9-1-1. Quando i servizi di emergenza sono abilitati, Skype for Business Server i client recuperano le informazioni sulla posizione al momento della registrazione e includono queste informazioni quando viene effettuata una chiamata di emergenza.
    
      - **Percorso**   Specificare uno dei valori seguenti:
        
          - **Richiesto**   All'utente verrà richiesta l'immissione delle informazioni sulla posizione quando il client si registra in una nuova posizione. L'utente può ignorare la richiesta e non immettere alcuna informazione. Se le informazioni vengono immesse, alla chiamata di emergenza effettuata risponderà innanzitutto il provider dei servizi di emergenza per verificare la posizione prima dell'instradamento al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point).
        
          - **Non richiesto**   All'utente non verrà richiesto di immettere la posizione. Quando viene effettuata una chiamata senza informazioni sulla posizione, il provider dei servizi di emergenza risponderà alla chiamata e richiederà la posizione.
        
          - **Dichiarazione di non responsabilità**   Questa opzione è uguale a **Obbligatorio,** tranne per il fatto che l'utente non può ignorare il prompt senza immettere le informazioni sulla posizione. L'utente può comunque effettuare una chiamata di emergenza, ma non è possibile effettuare altre chiamate senza immettere le informazioni. Viene inoltre visualizzato il testo della dichiarazione di non responsabilità per comunicare all'utente le conseguenze derivanti dal rifiuto di immettere le informazioni sulla posizione. Per impostare il testo della dichiarazione di non responsabilità, è necessario utilizzare Skype for Business Server Management Shell per eseguire il cmdlet **Set-CsLocationPolicy** o il cmdlet **New-CsLocationPolicy** con il parametro EnhancedEmergencyServiceDisclaimer. Per informazioni dettagliate, [vedere Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) o [New-CsLocationPolicy.](/powershell/module/skype/New-CsLocationPolicy)
          
    
      - **Usa la posizione solo per** i servizi di Skype for Business può usare le informazioni sulla posizione per vari motivi (ad esempio, per informare i membri del team della posizione corrente). Selezionare questa casella di controllo per verificare che le informazioni sulla posizione siano disponibili solo per l'utilizzo con una chiamata di emergenza.
    
      - **Utilizzo PSTN**   L'utilizzo PSTN (Public Switched Telephone Network) che verrà impiegato per determinare la route vocale utilizzata per instradare le chiamate di emergenza dai client che utilizzano questo profilo. La route associata a tale utilizzo deve puntare a un trunk SIP dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al punto di raccolta PSAP più vicino.
    
      - **Numero di composizione di emergenza**   Il numero che viene composto per chiamare i servizi di emergenza. Negli Stati Uniti il numero è 911. La stringa deve essere costituita da cifre comprese tra 0 e 9 e avere una lunghezza massima di 10 cifre.
    
      - **Maschera di composizione di emergenza**   Un numero che si desidera venga convertito nel valore del numero di composizione di emergenza quando viene composto. Ad esempio, se si immette 212 in questo campo mentre nel campo del numero di composizione di emergenza il valore è 911, quando un utente compone 212, la chiamata viene comunque effettuata al 911. In questo modo viene consentita la composizione di numeri di emergenza alternativi per raggiungere comunque i servizi di emergenza (ad esempio, se una persona proveniente da un altro paese con un diverso numero di emergenza tenta di comporre il numero di quel paese anziché il numero del paese in cui si trova attualmente). È possibile definire più maschere di composizione del numero di emergenza separando i valori con un punto e virgola, ad esempio 212;414. La lunghezza massima della stringa è 100 caratteri. Ogni carattere deve essere una cifra compresa tra 0 e 9.
      

        > [!IMPORTANT]  
        > Accertarsi che il valore specificato come maschera di composizione non corrisponda a un numero dell'intervallo di codici orbit del parcheggio di chiamata. L'instradamento del parcheggio di chiamata avrà infatti la precedenza sulla conversione delle stringhe di composizione per le chiamate di emergenza. Per visualizzare gli intervalli di codici orbit del parcheggio di chiamata esistenti, fare clic su **Funzionalità vocali** nella barra di spostamento sinistra e quindi fare clic su **Parcheggio di chiamata**. 

    
      - **URI notifica**   Uno o più URI (Uniform Resource Identifier) SIP a cui inviare una notifica quando viene effettuata una chiamata di emergenza. Ad esempio, l'ufficio che si occupa della sicurezza aziendale potrebbe ricevere una notifica tramite messaggio istantaneo ogni volta che viene effettuata una chiamata di emergenza. Se la posizione del chiamante è disponibile, verrà inclusa nella notifica. Per includere più URI SIP, utilizzare un elenco separato da virgole, ad esempio "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Le liste di distribuzione non sono supportate. La stringa deve avere una lunghezza compresa tra 1 e 256 caratteri e deve iniziare con il prefisso "sip:". Prima di fare clic nel campo URI notifica, viene visualizzato un esempio.
    
      - **URI conferenza**   L'URI SIP, in questo caso il numero di telefono, di terze persone che parteciperanno alle chiamate di emergenza effettuate. Ad esempio, l'ufficio che si occupa della sicurezza aziendale potrebbe ricevere una chiamata quando viene effettuata una chiamata di emergenza e ascoltare o partecipare alla chiamata (in base al valore specificato nel campo **Modalità conferenza**). La stringa deve avere una lunghezza compresa tra 1 e 256 caratteri e deve iniziare con il prefisso sip:. Finché non si fa clic in questo campo, viene visualizzato un esempio.
    
      - **Modalità conferenza**   Se si specifica un valore nel campo **URI conferenza**, l'impostazione del campo **Modalità conferenza** determinerà se terze persone possono partecipare alla chiamata o solo ascoltare. Selezionare una delle opzioni seguenti:
        
          - **Unidirezionale**   Terze persone possono solo ascoltare la conversazione tra il chiamante e l'operatore del centro PSAP.
        
          - **Bidirezionale**   Terze persone possono ascoltare e partecipare alla chiamata tra il chiamante e l'operatore del centro PSAP.

6.  Fare clic su **Commit**.


    > [!IMPORTANT]  
    > Quando si crea un criterio utente, inizialmente tale criterio non si applica ad alcun utente o sito di rete. Per applicare il criterio a un utente, fare clic **su Utenti** nella barra di spostamento sinistra. Individuare l'utente a cui si desidera applicare il criterio. Scegliere **Mostra dettagli** dal menu **Modifica**. Nella pagina **Modifica utente server** selezionare il nuovo criterio percorso nell'elenco a discesa **Criteri** percorso e quindi fare clic su **Commit**.<BR>Per applicare il criterio a un sito di rete, fare clic su **Configurazione di rete** sulla barra di spostamento sinistra, fare clic su **Sito**, individuare il sito di rete a cui applicare il criterio, scegliere **Mostra dettagli** dal menu **Modifica** e in **Modifica sito** selezionare il nuovo criterio percorso nell'elenco a discesa **Criteri percorso**, quindi fare clic su **Commit**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Per modificare un criterio percorso nel Pannello Skype for Business Server di controllo

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Criteri **percorso.**

4.  Nella pagina **Criteri percorso** selezionare il criterio percorso che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **Modifica criteri percorso** modificare i campi in base alle proprie esigenze. Per informazioni dettagliate, vedere il passaggio 5 nelle procedure "Per creare un nuovo criterio percorso" più indietro in questo argomento.

7.  Fare clic su **Commit**.

        
## <a name="delete-a-location-policy"></a>Eliminare un criterio percorso


1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Criteri **percorso.**

4.  Nella pagina  **Criteri percorso** selezionare il criterio percorso che si desidera eliminare.
   
    > [!NOTE]  
    > È possibile eliminare più criteri percorso contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare i diversi criteri. In alternativa, per selezionare tutti i criteri, scegliere  **Seleziona tutto** dal menu  **Modifica**.


5.  Scegliere  **Elimina** dal menu  **Modifica**.

6.  Fare clic su **OK**.

    > [!IMPORTANT]  
    > Non è possibile eliminare il criterio percorso Globale. Se si tenta di eliminare tale criterio, verrà visualizzato un messaggio di avviso e il criterio verrà reimpostato sui relativi valori predefiniti.


## <a name="see-also"></a>Vedere anche

[Creare o modificare siti di rete](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](/powershell/module/skype/Get-CsLocationPolicy)