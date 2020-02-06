---
title: Gestire le 9-1-1 avanzate e il servizio posizione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server supporta le chiamate avanzate di 9-1-1 (E9-1-1) dai client Skype for business. Quando si configura Skype for Business Server per E9-1-1, le chiamate di emergenza effettuate da Skype for business includono le informazioni sulla posizione di risposta alle emergenze dal database del servizio informazioni sulla posizione.
ms.openlocfilehash: de02c4a9a3210220e368d87d4ae8e21a80f3dbac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818427"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Gestire le funzionalità avanzate di 9-1-1 e il servizio posizione in Skype for busines server

Skype for Business Server supporta le chiamate avanzate di 9-1-1 (E9-1-1) dai client Skype for business. Quando si configura Skype for Business Server per E9-1-1, le chiamate di emergenza effettuate da Skype for business includono le informazioni sulla posizione di risposta alle emergenze dal database del servizio informazioni sulla posizione. Usare le procedure descritte in questo articolo per gestire i criteri di posizione.

> [!Note]
> Per informazioni dettagliate sulla distribuzione di funzionalità vocali avanzate per l'organizzazione, ad esempio E9-1-1 e il servizio informazioni sulla posizione, vedere [distribuire le funzionalità vocali avanzate di Enterprise](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).

In Skype for Business Server è possibile usare i criteri di posizione per applicare le impostazioni relative alle funzionalità avanzate di 9-1-1 (E9-1-1) e alle impostazioni della posizione per gli utenti o i contatti. I criteri di posizione determinano se un utente è abilitato per E9-1-1 e, in caso affermativo, qual è il comportamento di una chiamata di emergenza. Ad esempio, è possibile usare i criteri di posizione per definire il numero che costituisce una chiamata di emergenza, ad esempio 911 negli Stati Uniti, se la sicurezza aziendale deve essere notificata automaticamente e come deve essere instradata la chiamata.

È possibile configurare i criteri di posizione dal gruppo **configurazione di rete** nel pannello di controllo di Skype for Business Server. Nel pannello di controllo di Skype for Business Server è possibile visualizzare, creare, modificare o eliminare i criteri di posizione. Usare la procedura seguente per visualizzare informazioni sui criteri di posizione. 


## <a name="view-location-policy-information"></a>Visualizzare le informazioni sui criteri di posizione 

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **criteri posizione**.

4.  Nella pagina **criteri di posizione** selezionare i criteri di posizione che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.
 
    > [!NOTE]  
    > È possibile visualizzare solo le informazioni su un criterio di posizione alla volta.

Un singolo criterio, denominato globale, esiste per impostazione predefinita e non può essere eliminato o rinominato. È tuttavia possibile modificare il criterio globale. Questo criterio si applica a tutti gli utenti e i contatti, a meno che non si creino criteri del sito o criteri per utente. I criteri per utente devono essere applicati a utenti specifici.


## <a name="create-or-modify-a-location-policy"></a>Creare o modificare un criterio di posizione 

In Skype for Business Server è possibile ignorare la quantità di tempo predefinita tra le richieste client per un aggiornamento della posizione dal servizio informazioni sulla posizione. Il valore predefinito è 4 ore. Usa il cmdlet **Set-CsLocationPolicy** con il parametro LocationRefreshInterval per eseguire l'override del valore predefinito.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Per creare un nuovo criterio di posizione nel pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **criteri posizione**.

4.  Nella pagina **criteri di posizione** fare clic su **nuovo** e quindi selezionare il tipo di criterio da creare:
    
      - Per creare un criterio sito, fare clic su **criteri sito**. In **Seleziona un sito**scegliere il sito a cui si vuole applicare il criterio e fare clic su **OK**. Nella pagina **nuovo criterio di posizione** il campo **ambito** contiene il **sito**valore e il campo **nome** contiene il nome del sito scelto. Non è possibile modificare uno di questi campi. Un criterio di sito viene applicato automaticamente a tutti gli utenti nel sito specificato ed esegue l'override dei criteri globali per tali utenti.
    
      - Per creare un **criterio utente**, fare clic su **criteri utente**. Nei **nuovi criteri di posizione**il campo **ambito** contiene il valore **User**. Non è possibile modificare questo valore. Nel campo **nome** Digitare il nome che si vuole assegnare a questo criterio. Un criterio utente non si applica automaticamente agli utenti. Dopo aver creato il criterio utente, è necessario concedere manualmente il criterio agli utenti o ai siti di rete a cui si vuole applicare il criterio.

5.  Compilare i campi rimanenti come indicato di seguito:
    
      - **Abilita servizi di emergenza avanzati**   Selezionare questa casella di controllo per abilitare gli utenti associati al criterio per il servizio E9-1-1. Quando i servizi di emergenza sono abilitati, i client di Skype for Business Server recupereranno le informazioni sulla posizione sulla registrazione e includono tali informazioni quando viene effettuata una chiamata di emergenza.
    
      - **Posizione**   specifica uno dei valori seguenti:
        
          - **Obbligatorio**   l'utente verrà richiesto di immettere le informazioni sulla posizione quando il client viene registrato in una nuova posizione. L'utente può chiudere la richiesta senza immettere le informazioni. Se vengono immesse informazioni, una chiamata di emergenza verrà prima di tutto risolta dal provider di servizi di emergenza per verificare la posizione prima di essere instradata all'operatore PSAP (Public Safety Answering Point), ovvero l'operatore di 911.
        
          - **Non è necessario**   che l'utente non venga richiesto per una posizione. Quando si effettua una chiamata senza informazioni sulla posizione, il provider di servizi di emergenza risponderà alla chiamata e richiederà una posizione.
        
          - **Dichiarazione**   di non responsabilità questa opzione è la stessa **richiesta** , ad eccezione del fatto che l'utente non può chiudere la richiesta senza immettere le informazioni sulla posizione. L'utente può comunque completare una chiamata di emergenza, ma non possono essere completate altre chiamate senza immettere le informazioni. Inoltre, il testo della dichiarazione di non responsabilità verrà visualizzato all'utente che può avvisare le conseguenze della diminuzione per immettere le informazioni sulla posizione. Per impostare il testo della dichiarazione di non responsabilità, è necessario usare Skype for Business Server Management Shell per eseguire il cmdlet **Set-CsLocationPolicy** o il cmdlet **New-CsLocationPolicy** con il parametro EnhancedEmergencyServiceDisclaimer. Per informazioni dettagliate, vedere [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) o [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Usare la posizione solo per i servizi di emergenza** Skype for business può usare le informazioni sulla posizione per diversi motivi, ad esempio per segnalare ai membri del team la posizione corrente. Selezionare questa casella di controllo per assicurarsi che le informazioni sulla posizione siano disponibili solo per l'uso con una chiamata di emergenza.
    
      - **Uso PSTN l'**   utilizzo PSTN (Public Switched Telephone Network) che verrà usato per determinare quale route vocale verrà usata per instradare chiamate di emergenza da client che usano questo profilo. La route associata a tale utilizzo deve puntare a un trunk SIP dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) più vicino.
    
      - **Numero di telefono di emergenza**   il numero composto per raggiungere i servizi di emergenza. Negli Stati Uniti questo valore è 911. La stringa deve essere composta dalle cifre da 0 a 9 e può essere di lunghezza da 1 a 10 cifre.
    
      - **Maschera di emergenza digitare**   un numero che si vuole tradurre nel valore del valore del numero di telefono di emergenza quando viene composto. Ad esempio, se si immette un valore di 212 in questo campo e il campo numero di chiamata di emergenza ha un valore di 911, se un utente compone 212 la chiamata verrà eseguita a 911. In questo modo, i numeri di emergenza alternativi devono essere composti e i servizi di emergenza REACH (ad esempio, se qualcuno di un paese o di un'area geografica con un numero di emergenza diverso cerca di chiamare il numero del paese o dell'area geografica invece del numero paese o area geografica in cui si trovano attualmente. Puoi definire più maschere di chiamate di emergenza separando i valori con punti e virgola. Ad esempio, 212; 414. La lunghezza massima della stringa è di 100 caratteri. Ogni carattere deve essere una cifra da 0 a 9.
      

        > [!IMPORTANT]  
        > Verificare che il valore della maschera di chiamata specificata non sia uguale a un numero in un intervallo di orbit del parcheggio delle chiamate. Il routing di Call Park avrà la precedenza sulla conversione delle stringhe di chiamata di emergenza. Per visualizzare gli intervalli di Orbit di Call Park esistenti, fare clic su **funzionalità vocali** nella barra di spostamento sinistra e quindi su **Call Park**. 

    
      - **URI di notifica**   uno o più identificatori URI (Uniform Resource Identifier) SIP per ricevere una notifica quando viene effettuata una chiamata di emergenza. Ad esempio, l'ufficio sicurezza aziendale può essere avvisato tramite un messaggio istantaneo ogni volta che viene effettuata una chiamata di emergenza. Se la posizione del chiamante è disponibile, tale posizione verrà inclusa nella notifica. Più URI SIP possono essere inclusi come elenco delimitato da virgole. Ad esempio, "SIP: security@litwareinc. com", "SIP: kmyer@litwareinc. com". Le liste di distribuzione sono supportate. La stringa deve essere da 1 a 256 caratteri di lunghezza e deve iniziare con il prefisso "SIP:". Prima di fare clic nel campo URI di notifica viene visualizzato un esempio.
    
      - **URI conferenza l'**   URI SIP, in questo caso il numero di telefono, di una terza persona che verrà convocata per le chiamate di emergenza effettuate. Ad esempio, l'ufficio sicurezza aziendale può ricevere una chiamata quando viene effettuata una chiamata di emergenza e ascoltare o partecipare a tale chiamata (a seconda del valore fornito nel campo **modalità conferenza** ). La stringa deve avere una lunghezza compresa tra 1 e 256 caratteri e deve iniziare con il prefisso sip:. Viene visualizzato un esempio finché non si fa clic all'interno di questo campo.
    
      - **Modalità**   conferenza se si specifica un valore nel campo **URI conferenza** , la **modalità conferenza** determina se una terza parte può partecipare alla chiamata o può solo ascoltare. Specificare una delle opzioni seguenti:
        
          - **La sola modalità**   di una terza parte può essere ascoltata solo dalla conversazione tra il chiamante e l'operatore PSAP.
        
          - **A due vie**   una terza parte può ascoltare e partecipare alla chiamata tra il chiamante e l'operatore PSAP.

6.  Fare clic su **Commit**.


    > [!IMPORTANT]  
    > Quando si crea un criterio utente, inizialmente i criteri non si applicano a utenti o siti di rete. Per applicare il criterio a un utente, fare clic su **utenti** nella barra di spostamento sinistra. Individuare l'utente a cui si vuole applicare il criterio. Nel menu **modifica** fare clic su **Mostra dettagli**. Nella pagina **Edit Server User** selezionare i nuovi criteri di posizione dall'elenco a discesa **criteri di posizione** e quindi fare clic su **commit**.<BR>Per applicare il criterio a un sito di rete, fare clic su **configurazione di rete** nella barra di spostamento sinistra e quindi fare clic su **sito**. Individuare il sito di rete a cui si vuole applicare il criterio. Nel menu **modifica** fare clic su **Mostra dettagli**. In **modifica sito**selezionare i nuovi criteri di posizione dall'elenco a discesa **criteri di posizione** e quindi fare clic su **commit**.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Per modificare un criterio di posizione nel pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **criteri posizione**.

4.  Nella pagina **criteri di posizione** selezionare i criteri di posizione che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **modifica criterio di posizione** modificare i campi in modo necessario (per informazioni dettagliate, vedere il passaggio 5 nella sezione "per creare un nuovo criterio di posizione" in precedenza in questo argomento).

7.  Fare clic su **Commit**.

        
## <a name="delete-a-location-policy"></a>Eliminare un criterio di posizione


1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **criteri posizione**.

4.  Nella pagina **criteri di posizione** selezionare i criteri di posizione che si desidera eliminare.
   
    > [!NOTE]  
    > È possibile eliminare più criteri di posizione alla volta. Per eseguire questa operazione, premere CTRL e selezionare più criteri tenendo premuto il tasto CTRL. In alternativa, per selezionare tutti i criteri, fare clic su **Seleziona tutto** dal menu **modifica** .


5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.

    > [!IMPORTANT]  
    > Non è possibile eliminare i criteri di posizione globale. Se si tenta di eliminare il criterio globale si riceverà un messaggio di avviso e il criterio verrà reimpostato sui valori predefiniti.


## <a name="see-also"></a>Vedere anche

[Creare o modificare siti di rete](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
