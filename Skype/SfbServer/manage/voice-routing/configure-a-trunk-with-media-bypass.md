---
title: Configurare un trunk con bypass multimediale in Skype for Business Server
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
description: 'Seguire questa procedura per configurare un trunk con bypass multimediale abilitato. '
ms.openlocfilehash: 861a57c50aa7092bf654fb626d4f1e94e3b3449539d33ead72b4925f8b102f4f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349248"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configurare un trunk con bypass multimediale in Skype for Business Server

Seguire questa procedura per configurare un trunk con bypass multimediale abilitato. Per configurare un trunk con bypass multimediale disabilitato, vedere [Configure a trunk without media bypass in Skype for Business Server](configure-a-trunk-without-media-bypass.md). La funzionalità bypass multimediale è utile se si desidera ridurre il numero dei Mediation Server distribuiti. Un pool Mediation Server viene in genere distribuito in un sito centrale e controlla i gateway nei siti di succursale. Abilitando il bypass multimediale, gli elementi multimediali per chiamate PSTN da client dei siti di succursale possono attraversare direttamente i gateway di tali siti. Skype for Business Server le route delle chiamate in uscita e i criteri VoIP aziendale devono essere configurati correttamente in modo che le chiamate PSTN provenienti dai client di un sito di succursale siano instradati al gateway appropriato.

Ti consigliamo vivamente di abilitare il bypass multimediale. Tuttavia, prima di abilitare il bypass multimediale in un trunk SIP, verificare che il provider trunk SIP qualificato supporti il bypass multimediale e sia in grado di soddisfare i requisiti per la corretta abilitazione dello scenario. In particolare, il provider deve disporre degli indirizzi IP dei server nella rete interna dell'organizzazione. Se il provider non è in grado di supportare questo scenario, non sarà possibile utilizzare il bypass multimediale. Per informazioni dettagliate, vedere [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> Il bypass multimediale non interagisce con ogni gateway PSTN (Public Switched Telephone Network), IP-PBX e Session Border Controller (SBC). Microsoft ha testato un set di gateway PSTN e SBC con partner certificati ed ha eseguito alcuni test con IP-PBC Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati nella pagina [Infrastruttura di telefonia per Skype for Business Server.](../../../SfbPartnerCertification/certification/infra-gateways.md) 


Una configurazione trunk come descritto di seguito raggruppa un set di parametri che vengono applicati ai trunk assegnati a questa configurazione trunk. Per una determinata configurazione trunk è possibile specificare un ambito globale (corrispondente a tutti i trunk che non presentano una configurazione di sito o di pool più specifica) o un ambito di sito o di pool. La configurazione trunk a livello di pool viene usata per definire un singolo trunk come ambito di una determinata configurazione trunk.

**Per configurare un trunk con bypass multimediale**

1. Aprire Skype per il Pannello di controllo del server Busines.
2. Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.
3. Nella pagina **Configurazione trunk** utilizzare uno dei metodi seguenti per configurare un trunk:
    - Fare doppio clic su un trunk esistente, ad esempio il trunk **Globale**, per visualizzare la finestra di dialogo **Modifica configurazione trunk**.
    - Fare clic su **Nuovo** e quindi selezionare un ambito per la nuova configurazione trunk:
        - **Trunk sito**: scegliere il sito per la configurazione trunk da **Selezionare un sito** e quindi fare clic su **OK.** Si noti che se è già stata creata una configurazione trunk per un sito, tale sito non verrà visualizzato in **Seleziona un sito**. La configurazione trunk verrà applicata a tutti i trunk presenti nel sito.
        - **Trunk del pool**: scegliere il nome del trunk a cui si applica questa configurazione trunk. Questo trunk può essere il trunk radice o qualsiasi altro trunk definito in Generatore di topologie. In **Selezionare un servizio** fare clic su **OK.** Si noti che se è già stata creata una configurazione trunk per un trunk specifico, tale trunk non verrà visualizzato in **Seleziona un servizio**.
    
    > [!NOTE]
    > Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo. Il campo **Nome** è già compilato con il nome del sito o del servizio associato alla configurazione trunk e non è possibile modificarlo. 

5. Specificare un valore in **Numero massimo di finestre di dialogo iniziali supportate**. Questo è il numero massimo di risposte forked che un gateway PSTN (Public Switched Telephone Network), IP-PBX o SBC (Session Border Controller) ITSP può ricevere a un invite inviato al Mediation Server. Il valore predefinito è 20.

    > [!NOTE] 
    > Prima di modificare questo valore, consultare il provider di servizi o il produttore delle apparecchiature per informazioni più dettagliate sulle capacità del sistema in uso. 

6. Selezionare una delle opzioni di **Livello di supporto crittografia** seguenti:
    - **Necessario**: è necessario usare la crittografia SRTP (Secure Real-time Transport Protocol) per proteggere il traffico tra il Mediation Server e il gateway o il PBX (Private Branch Exchange).
    - **Facoltativo**: la crittografia SRTP verrà utilizzata se supportata dal provider di servizi o dal produttore dell'apparecchiatura.
    - **Non supportato**: la crittografia SRTP non è supportata dal provider del servizio o dal produttore delle apparecchiature, pertanto non verrà utilizzata.
7. Selezionare la casella di controllo **Abilita bypass multimediale** se si desidera che gli elementi multimediali ignorino il Mediation Server per l'elaborazione da parte del trunk peer.

    > [!IMPORTANT]
    > Per un corretto funzionamento del bypass multimediale, è necessario che il gateway PSTN, il sistema IP-PBX o il Session Border Controller supporti determinate funzionalità. Per informazioni dettagliate, vedere [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Selezionare la casella di controllo **Elaborazione multimediale centralizzata** se esiste un punto di terminazione multimediale noto, ad esempio un gateway PSTN in cui la terminazione multimediale ha lo stesso IP della terminazione di segnalazione. Deselezionare la casella di controllo se il trunk non dispone di un punto di terminazione multimediale noto.
9. Se il trunk peer supporta la ricezione di richieste SIP REFER dal Mediation Server, selezionare la casella di controllo Abilita invio **riferimento al gateway.** 

    > [!NOTE] 
    > Se si disabilita questa opzione mentre è selezionata l'opzione **Abilita bypass multimediale** saranno necessarie ulteriori impostazioni. Se il trunk peer non supporta la ricezione di richieste SIP REFER dal Mediation Server ed è abilitato il bypass multimediale, sarà inoltre necessario eseguire il cmdlet **Set-CsTrunkConfiguration** per disabilitare RTCP per le chiamate attive e in attesa in modo da supportare le condizioni appropriate per il bypass multimediale. In alternativa, è  possibile selezionare Abilita riferimento utilizzando il controllo delle chiamate di terze parti se si desidera che le chiamate trasferite siano ignorate e il gateway non supporti le richieste SIP REFER. 

10. (Facoltativo) Per abilitare il routing tra trunk, associare e configurare i record utilizzo PSTN a questa configurazione trunk. Gli utilizzi PSTN associati a questa configurazione trunk verranno applicati a tutte le chiamate in arrivo tramite il trunk che non proviene da un endpoint Skype for Business Server remoto. Per gestire i record utilizzo PSTN associati a una configurazione trunk, usare uno di questi metodi:
    - Per selezionare uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Evidenziare i record da associare a questa configurazione trunk e quindi fare clic su **OK**.
    - Per rimuovere un record utilizzo PSTN da questa configurazione trunk, selezionare il record e fare clic su **Rimuovi**.
    - Per definire un nuovo record utilizzo PSTN e associarlo a questa configurazione trunk, eseguire le operazioni seguenti:
        1. Fare clic su **Nuovo**.
        2. Nel campo **Nome** specificare un nome descrittivo univoco per il record.
            > [!NOTE] 
            > Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo **Nome** non può essere modificato. 
        3. Per associare e configurare le route per questo record utilizzo PSTN, usare uno dei metodi seguenti:
            - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare a questo record utilizzo PSTN e fare clic su **OK**. 
            - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.
            - Per definire una nuova route e associarla a questo record utilizzo PSTN, fare clic su **Nuovo**. 
            - Per modificare una route associata a questo record utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**. 
        4. Fare clic su **OK**.
    - Per modificare un record utilizzo PSTN già associato a questa configurazione trunk, eseguire le operazioni seguenti:
        1. Selezionare il record utilizzo PSTN da modificare e fare clic su **Mostra dettagli**.
        2. Per associare e configurare le route per questo record utilizzo PSTN, usare uno dei metodi seguenti:
            - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare a questo record utilizzo PSTN e fare clic su **OK**. 
            - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.
            - Per definire una nuova route e associarla a questo record utilizzo PSTN, fare clic su **Nuovo**. 
            - Per modificare una route associata a questo record utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**. 
        3. Fare clic su **OK**.

    > [!Important]
    > È importante associare i record di utilizzo PSTN in base al peer Mediation Server associato al trunk da configurare. Se il peer Mediation Server è un gateway PSTN o un session border controller (SBC), è consigliabile non associare la configurazione trunk a un record di utilizzo PSTN che instrada a una destinazione PSTN o a qualsiasi altro sistema downstream connesso tramite Skype for Business Server. 

11. Organizzare i record utilizzo PSTN in modo da ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, selezionare il record utilizzo PSTN e fare clic sulle frecce verso l'alto o verso il basso.

    > [!Important]
    > L'ordine in cui i record utilizzo PSTN sono elencati nella configurazione trunk è significativo. Skype for Business Server attraversa l'elenco dall'alto verso il basso. 

12. **Abilita latch RTP** deve essere selezionato per abilitare i supporti di bypass per i client dietro un NAT (Network Address Translation) o un firewall e un SBC che supporta latching.
13. **Per abilitare l'invio** delle informazioni sulla cronologia delle chiamate al peer gateway del Mediation Server, è necessario selezionare Abilita cronologia chiamate di inoltro.
14. Abilitare l'inoltro dei dati **P-Asserted-Identity** per consentire l'inoltro delle informazioni sull'autore delle chiamate PAI (P-Asserted-Identity) tra il lato Mediation Server e il lato gateway (e viceversa), se presenti.
15. Per abilitare il failover rapido, selezionare **Abilita timer di failover del routing in uscita**. Il gateway associato a questo trunk può inviare una notifica entro 10 secondi dall'inizio dell'elaborazione di una chiamata in uscita. Se questa notifica non viene ricevuta dal Mediation Server, si verificherà il reindirizzamento a un altro trunk. Nelle reti in cui la latenza potrebbe ritardare il tempo di risposta o il gateway impiega più di 10 secondi per rispondere, è consigliabile disabilitare il failover rapido.
16. (Facoltativo) Associare e configurare le **Regole di conversione per il numero del chiamante** per il trunk. Queste regole di conversione si applicano al numero chiamante per le chiamate in uscita.
    - Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona.** In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.
    - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**. Per informazioni dettagliate, vedere [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**. Per informazioni dettagliate, vedere [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.
    > [!Warning]
    > Non associare regole di conversione a un trunk se nel peer trunk associato sono già configurate regole di conversione, poiché potrebbe verificarsi un conflitto tra le due regole. 

17. (Facoltativo) Associare e configurare le **Regole di conversione per il numero chiamato** per il trunk. Tali regole sono applicabili al numero chiamato in una chiamata in uscita.
    - Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona.** In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.
    - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**. Per informazioni dettagliate, vedere [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**. Per informazioni dettagliate, vedere [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

    > [!Warning] 
    > Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel peer trunk associato, perché le due regole potrebbero essere in conflitto. 

18. Assicurarsi che le regole di conversione del trunk siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e fare clic sulla freccia su o giù.

    >[!Important] 
    > Skype for Business Server l'elenco delle regole di conversione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto. Se si configura un trunk in modo che un numero che viene composto possa soddisfare più regole di conversione, verificare che le regole più restrittive siano elencate al di sopra di quelle meno restrittive. Se ad esempio sono state incluse una regola di conversione per qualsiasi numero di 11 cifre e una regola di conversione solo per i numeri di 11 cifre che iniziano con +1425, verificare che la regola per i numeri di 11 cifre sia elencata *al di sotto* della regola più restrittiva. 

19. Dopo aver terminato la configurazione del trunk, fare clic su **OK**.
20. Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**. 

    > [!Note]
    > Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). (SERVE NUOVO COLLEGAMENTO?)

Dopo aver configurato il trunk, continuare a configurare il bypass multimediale scegliendo tra le opzioni di bypass multimediale globali, come descritto [in Deploy media bypass in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md).