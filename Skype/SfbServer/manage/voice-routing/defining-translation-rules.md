---
title: Definizione delle regole di traduzione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server Enterprise Voice instrada le chiamate in base ai numeri di telefono normalizzati in formato E. 164. Questo significa che tutte le stringhe con chiamata devono essere normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL) in modo che possano essere convertite nell'URI SIP corrispondente. Skype for Business Server offre la possibilità di modificare l'ID chiamato e la presentazione dell'ID chiamante.
ms.openlocfilehash: 633b0c16fefb66d1ea44f96b5f32c2ca91f357f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187037"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definizione delle regole di traduzione in Skype for Business Server

Skype for Business Server Enterprise Voice instrada le chiamate in base ai numeri di telefono normalizzati in formato E. 164. Questo significa che tutte le stringhe con chiamata devono essere normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL) in modo che possano essere convertite nell'URI SIP corrispondente. Skype for Business Server offre la possibilità di modificare l'ID chiamato e la presentazione dell'ID chiamante.

Con Skype for Business Server, il numero di telefono della festa chiamata (ovvero il numero di telefono chiamato) può essere tradotto dal formato E. 164 al formato di chiamata locale richiesto dal peer trunk, ovvero il gateway associato, il PBX (Private Branch Exchange) o il SIP trunk). A tale scopo, è necessario definire una o più regole di traduzione per tradurre l'URI della richiesta prima di instradarlo al peer trunk.

## <a name="caller-id-presentation"></a>Presentazione dell'ID chiamante

Skype for Business Server offre la possibilità di tradurre anche il numero di telefono della parte chiamante (ovvero il numero di telefono da cui il chiamante chiama) dal formato E. 164 al formato di chiamata locale richiesto dal peer trunk. Ad esempio, è possibile scrivere una regola di traduzione per rimuovere + 44 dall'inizio di una stringa di chiamata e sostituirla con 0144.

**Per configurare l'ID chiamante tramite il pannello di controllo di Skype for Business Server**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le [autorizzazioni di configurazione](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for business, vedere [installare e aprire strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **configurazione trunk**.
4. Nella pagina trunk Configuration fare doppio clic su un trunk esistente, ad esempio il trunk **globale** , per visualizzare la finestra di dialogo **modifica configurazione trunk** .
5. Per configurare la presentazione dell'ID chiamante:
    - Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. In **regole di traduzione dei numeri di chiamata**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.
    - Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**. 
    - Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**.
    - Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola, fare clic su **copia**e quindi su **Incolla**.
    - Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

> [!Warning] 
> Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto. 

## <a name="called-id-presentation"></a>Chiamata presentazione ID

> [!Important]
> La possibilità di associare una o più regole di traduzione a una configurazione trunk VoIP aziendale è destinata a essere usata come *alternativa* alla configurazione delle regole di traduzione nel trunk peer. Non associare regole di traduzione a una configurazione trunk VoIP aziendale se sono state configurate regole di traduzione nel peer trunk perché le due regole potrebbero essere in conflitto. 

Puoi usare uno dei metodi seguenti per creare o modificare una regola di traduzione:

- [Usare lo strumento Costruisci una regola di traduzione](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere e quindi consentire al pannello di controllo di Skype for Business Server di generare automaticamente il modello di corrispondenza e la regola di traduzione corrispondenti.
- [Scrivere manualmente le espressioni regolari](#create-or-modify-a-translation-rule-manually) per definire il modello e la regola di traduzione corrispondenti.

> [!Note]
> Per informazioni su come scrivere espressioni regolari, vedere [espressioni regolari di .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Creare o modificare una regola di traduzione usando lo strumento crea una regola di traduzione

Seguire questa procedura se si vuole definire una regola di traduzione immettendo un set di valori nello strumento compila una regola di traduzione e abilitando il pannello di controllo di Skype for Business Server per generare la regola di corrispondenza corrispondente e le regole di traduzione. 

**Per definire una regola usando lo strumento crea una regola di traduzione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le [autorizzazioni di configurazione](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for business, vedere [installare e aprire strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Per iniziare a definire una regola di traduzione, seguire i passaggi descritti in [configurare un trunk con il bypass multimediale](GET LINK AFTER MIGRATION)tramite il passaggio 10 o [configurare un trunk senza bypass multimediale](GET LINK AFTER MIGRATION) tramite il passaggio 9.
4. In **nome** nella pagina **nuova** regola di traduzione o **Modifica regola di traduzione** digitare un nome che descriva il modello di numero da tradurre.
5. Opzionale In **Descrizione**Digitare una descrizione della regola di traduzione, ad esempio le **chiamate interurbane internazionali degli Stati Uniti**.
6. Nella sezione **genera una regola di traduzione** della finestra di dialogo immettere i valori nei campi seguenti:
    - **Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si vuole che corrisponda il motivo. Ad esempio, immettere + in questo campo per abbinare i numeri nel formato E. 164 (che iniziano con +).
    - **Length**: specificare il numero di cifre nel criterio di corrispondenza e selezionare se si vuole che il pattern corrisponda a numeri di lunghezza uguale a quella specificata, almeno questa lunghezza o qualsiasi lunghezza. Ad esempio, immetti **11** e **** seleziona almeno nell'elenco a discesa per abbinare i numeri di almeno 11 cifre in lunghezza.
    - **Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da eliminare. Ad esempio, immettere **1** per eliminare il + dall'inizio del numero.
    - **Cifre da aggiungere**: (facoltativo) specificare le cifre da anteporre ai numeri tradotti. Ad esempio, immetti **011** se vuoi che 011 venga anteposto ai numeri tradotti quando viene applicata la regola.
    
    I valori immessi in questi campi si riflettono nei campi della regola **per la corrispondenza** e la **traduzione** . Ad esempio, se specifichi i valori di esempio precedenti, l'espressione regolare risultante nel campo **pattern to matc**h è:
    
    **^\+(\d{9}\d +) $** 

    Il campo della **regola di traduzione** specifica un modello per il formato dei numeri tradotti. Questo modello include due parti:
    - Un valore, ad esempio **$1**, che rappresenta il numero di cifre nel modello corrispondente
    - Opzionale Un valore che puoi anteporre immettendolo nel campo **cifre da aggiungere**

    Usando i valori di esempio precedenti, viene visualizzato **011 $1** nel campo della **regola di traduzione** .
    
    Quando viene applicata questa regola di traduzione, + 441235551010 diventa 011441235551010.
7. Fare clic su **OK** per salvare la regola di traduzione.
8. Fare clic su **OK** per salvare la configurazione trunk.
9. Nella pagina **trunk configuratio**n fare clic su **commit**e quindi su **Commit all**. 

> [!Note]
> Ogni volta che si crea o si modifica una regola di traduzione, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso nella configurazione del routing vocale](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Creare o modificare manualmente una regola di traduzione

Seguire questa procedura se si vuole definire una regola di traduzione scrivendo un'espressione regolare per il modello e la regola di traduzione corrispondenti. 

**Per definire manualmente una regola di traduzione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le [autorizzazioni di configurazione](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for business, vedere [installare e aprire strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Per iniziare a definire una regola di traduzione, seguire i passaggi descritti in [configurare un trunk con il bypass multimediale](GET LINK AFTER MIGRATION)tramite il passaggio 10 o [configurare un trunk senza bypass multimediale](GET LINK AFTER MIGRATION) tramite il passaggio 9.
4. Nel campo **nome** della pagina **nuova** regola di traduzione o **Modifica regola di traduzione** digitare un nome che descriva il modello di numero da tradurre.
5. Opzionale In **Descrizione**Digitare una descrizione della regola di traduzione; ad esempio, le **chiamate interurbane internazionali degli Stati Uniti**.
6. Fare clic su **modifica** nella parte inferiore della sezione **Compila una regola di traduzione** .
7. Immettere le opzioni seguenti nell' **espressione regolare**di tipo:
    - In **Confronta questo modello**, specifica il motivo che verrà usato per corrispondere ai numeri da tradurre.
    - Nella **regola di traduzione**specificare un motivo per il formato dei numeri tradotti.

    Ad esempio, se immetti ** ^ \+(\d{9}\d +) $** in **corrisponde a questo modello** e **011 $1** nella **regola di traduzione**, la regola tradurrà + 441235551010 in 011441235551010.
8. Fare clic su **OK** per salvare la regola di traduzione.
9. Fare clic su **OK** per salvare la configurazione trunk.
10. Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**. 

> [!Note] 
> Ogni volta che si crea o si modifica una regola di traduzione, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso nella configurazione del routing vocale](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 
