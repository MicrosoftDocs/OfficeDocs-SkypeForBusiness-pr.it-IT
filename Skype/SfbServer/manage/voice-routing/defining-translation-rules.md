---
title: Definizione delle regole di conversione in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: Skype for Business Server VoIP aziendale le chiamate in base ai numeri di telefono normalizzati nel formato E.164. Ciò significa che tutte le stringhe componete devono essere normalizzate nel formato E.164 allo scopo di eseguire la ricerca di numeri inversa (RNL) in modo che possano essere convertite nell'URI SIP corrispondente. Skype for Business Server consente di modificare l'ID chiamato e la presentazione dell'ID chiamante.
---

# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definizione delle regole di conversione in Skype for Business Server

Skype for Business Server VoIP aziendale le chiamate in base ai numeri di telefono normalizzati nel formato E.164. Ciò significa che tutte le stringhe componete devono essere normalizzate nel formato E.164 allo scopo di eseguire la ricerca di numeri inversa (RNL) in modo che possano essere convertite nell'URI SIP corrispondente. Skype for Business Server consente di modificare l'ID chiamato e la presentazione dell'ID chiamante.

Con Skype for Business Server, il numero di telefono della parte chiamata ,ovvero il numero di telefono chiamato, può essere convertito dal formato E.164 al formato di composizione locale richiesto dal trunk peer, ovvero dal gateway associato, dal PBX (Private Branch Exchange) o dal trunk SIP. A tale scopo, è necessario definire una o più regole per la conversione dell'URI di richiesta prima del routing al peer trunk.

## <a name="caller-id-presentation"></a>Presentazione DELL'ID chiamante

Skype for Business Server offre la possibilità di convertire anche il numero di telefono della parte chiamante (ovvero il numero di telefono da cui il chiamante sta chiamando) dal formato E.164 al formato di composizione locale richiesto dal trunk peer. È ad esempio possibile scrivere una regola di conversione per rimuovere +44 da una stringa di composizione e sostituirlo con 0144.

**Per configurare l'ID chiamante utilizzando il Skype for Business Server pannello di controllo**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [Delegate setup permissions](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Skype for Business di controllo, vedere [Installare e aprire gli strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.
4. Nella pagina Configurazione trunk fare doppio clic su un trunk esistente, ad esempio il trunk **Globale** per visualizzare la finestra di dialogo **Modifica configurazione trunk**.
5. Per configurare la presentazione dell'ID chiamante:
    - Per selezionare una o più regole in un elenco di tutte le regole di conversione disponibili nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. In **Regola di conversione per il numero del chiamante** fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.
    - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. 
    - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**.
    - Per copiare una regola di conversione esistente da utilizzare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola, su **Copia e quindi** su **Incolla**.
    - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

> [!Warning] 
> Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel peer trunk associato, perché le due regole potrebbero essere in conflitto. 

## <a name="called-id-presentation"></a>Presentazione ID chiamata

> [!Important]
> La possibilità di associare una o più regole di conversione a una configurazione trunk VoIP aziendale è progettata per essere utilizzata come  alternativa alla configurazione delle regole di conversione nel trunk peer. Non associare regole di conversione a una VoIP aziendale trunk se sono state configurate regole di conversione nel trunk peer perché le due regole potrebbero essere in conflitto. 

È possibile utilizzare uno dei metodi seguenti per creare e modificare una regola di conversione:

- [](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) Utilizzare lo strumento Crea regola di conversione per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere e quindi lasciare che il Pannello di controllo di Skype for Business Server generi automaticamente il modello di corrispondenza e la regola di conversione corrispondenti.
- [Scrivere manualmente le espressioni regolari per](#create-or-modify-a-translation-rule-manually) definire il modello di corrispondenza e la regola di conversione.

> [!Note]
> Per informazioni su come scrivere espressioni regolari, vedere .NET Framework [regolari](/dotnet/standard/base-types/regular-expressions). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione

Seguire questa procedura se si desidera definire una regola di conversione immettendo un set di valori nello strumento Crea regola di conversione e abilitando il Pannello di controllo di Skype for Business Server per generare automaticamente il modello di corrispondenza e la regola di conversione corrispondenti. 

**Per definire una regola tramite lo strumento Crea regola di conversione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [Delegate setup permissions](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Skype for Business di controllo, vedere [Installare e aprire gli strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Per iniziare a definire una regola di conversione, seguire i passaggi descritti in [Configure a trunk with media bypassthrough](GET LINK AFTER MIGRATION) step 10 o [Configure a trunk without media bypass](GET LINK AFTER MIGRATION) through through step 9.
4. In **Nome** nella pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome descrittivo del formato del numero da convertire.
5. (Facoltativo) In **Descrizione** digitare una descrizione della regola di conversione, ad esempio Composizione **interurbana internazionale negli Stati Uniti**.
6. Nella sezione **Crea regola di conversione** della finestra di dialogo immettere i valore nei campi seguenti:
    - **Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si desidera corrisponda il formato. Ad esempio, immettere + in questo campo per specificare una corrispondenza con i numeri nel formato E.164, che iniziano con +.
    - **Lunghezza**: specificare il numero di cifre nel formato e specificare se si desidera applicare il formato ai numeri esattamente di questa lunghezza, almeno di questa lunghezza o di qualsiasi lunghezza. Ad esempio, immettere **11** e selezionare **Almeno** nell'elenco a discesa per specificare una corrispondenza con i numeri con una lunghezza di almeno 11 cifre.
    - **Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da rimuovere. Ad esempio, immettere **1** per rimuovere il + all'inizio del numero.
    - **Prefisso**: (facoltativo) specificare le cifre da aggiungere all'inizio dei numeri convertiti. Ad esempio, immettere **011** se si desidera aggiungere 011 all'inizio dei numeri convertiti quando si applica questa regola.
    
    I valori immessi in questi campi si riflettono nei campi Criterio di corrispondenza **e** **Regola di** conversione. Se ad esempio si specificano i valori di esempio precedenti, l'espressione regolare risultante nel campo **Da modello a match** sarà la seguente:
    
    **^\+(\d{9}\d+)$** 

    Nel campo **Regola di conversione** specificare un modello per il formato dei numeri convertiti. Il modello è composto da due parti:
    - Un valore (ad esempio **$1**) che rappresenta il numero di cifre nel formato corrispondente
    - (Facoltativo) Un valore che è possibile aggiungere all'inizio del numero immettendolo nel campo **Prefisso**

    In base ai valori di esempio precedenti, nel campo **Regola di conversione** viene visualizzato **011$1**.
    
    Con l'applicazione di questa regola di conversione il numero +441235551010 diventa 011441235551010.
7. Fare clic su **OK** per salvare la regola di conversione.
8. Fare clic su **OK** per salvare la configurazione del trunk.
9. Nella pagina **Trunk Configuration** fare clic su **Commit** e quindi su **Commit tutto**. 

> [!Note]
> Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Creare o modificare manualmente una regola di conversione

Eseguire questa procedura se si desidera definire una regola di conversione scrivendo un'espressione regolare per il formato e la regola. 

**Per definire manualmente una regola di conversione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [Delegate setup permissions](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Skype for Business di controllo, vedere [Installare e aprire gli strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Per iniziare a definire una regola di conversione, seguire i passaggi descritti in [Configure a trunk with media bypassthrough](GET LINK AFTER MIGRATION) step 10 o [Configure a trunk without media bypass](GET LINK AFTER MIGRATION) through through step 9.
4. Nel campo **Nome** della pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome che descriva il formato del numero da convertire.
5. (Facoltativo) In **Descrizione** digitare una descrizione della regola di conversione. ad esempio, **composizione interurbana internazionale degli Stati Uniti**.
6. Fare clic su **Modifica** nella parte inferiore della sezione **Crea regola di conversione**.
7. Immettere quanto segue in Digitare **un'espressione regolare**:
    - In **Trova corrispondenza per questo formato** specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire.
    - In **Regola di conversione** specificare un modello per il formato dei numeri convertiti.

    Ad esempio, se **^\+immetti (\d{9}\d+)$** **in Corrispondenza** questo modello e **011$1** **in Regola** di conversione, la regola convertirà +441235551010 in 011441235551010.
8. Fare clic su **OK** per salvare la regola di conversione.
9. Fare clic su **OK** per salvare la configurazione del trunk.
10. Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**. 

> [!Note] 
> Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration).