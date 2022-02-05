---
title: Creare o modificare una route vocale in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Riepilogo: informazioni su come creare o modificare una route vocale in Skype for Business Server utilizzando il Pannello Skype for Business Server di controllo.'
---

# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Creare o modificare una route vocale in Skype for Business
 
**Riepilogo:** Informazioni su come creare o modificare una route vocale in Skype for Business Server utilizzando il Pannello Skype for Business Server di controllo.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Per creare una route vocale tramite il Pannello Skype for Business Server comandi

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator** .
    
2. Aprire Skype for Business Server Pannello di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Routing vocale**.
    
4. Fare clic su **Route**.
    
5. Fare **clic su Nuovo** per visualizzare la **finestra di dialogo Nuova route** vocale.
    
6. In **Nome** digitare un nome descrittivo per la route vocale.
    
7. (Facoltativo) In **Descrizione** digitare ulteriori informazioni descrittive per la route vocale.
    
8. Per specificare i modelli che si desidera supportare questa route, è possibile utilizzare lo strumento  Crea un modello per la corrispondenza per generare un'espressione regolare oppure scrivere l'espressione regolare manualmente.
    
   - Per utilizzare lo strumento **Formato per corrispondenza** per generare un'espressione regolare, immettere i valori come indicato di seguito. È possibile specificare due tipi di corrispondenze di formato:
    
   - **Cifre iniziali per i numeri da consentire**: immettere i valori di prefisso che la route deve includere, incluso il segno + iniziale, se necessario. Ad esempio, digitare +425 e quindi fare clic su **Aggiungi**. Ripetere questa operazione per ogni valore di prefisso da includere nella route.
    
   - **Eccezioni**: se si desidera specificare una o più eccezioni per un valore di prefisso, evidenziare il prefisso e fare clic su **Eccezioni**. Digitare uno o più valori per i modelli di corrispondenza che non  *si desidera*  che questa route supporti. Ad esempio, per escludere i numeri che iniziano con +425237 dalla route, immettere il valore +425237 nel campo Eccezioni e quindi  fare clic su **OK**.
    
   - Per definire manualmente il formato di corrispondenza, fare clic su **Modifica** nello strumento **Formato per corrispondenza** e quindi digitare un'espressione regolare .NET Framework per specificare il formato di corrispondenza per i numeri di telefono di destinazione ai quali viene applicata la route. Per informazioni dettagliate su come scrivere espressioni regolari, vedere [".NET Framework regolari"](/dotnet/standard/base-types/regular-expressions). 
    
9. Selezionare **Ometti ID chiamante** se non si desidera che l'ID del telefono che effettua la chiamata in uscita venga visualizzato al destinatario della chiamata. Se si seleziona questa opzione, è necessario specificare un **ID** chiamante alternativo che verrà visualizzato nella visualizzazione dell'ID chiamante del destinatario.
    
10. Per associare uno o più trunk alla route vocale, fare clic su **Aggiungi** e quindi selezionare un trunk nell'elenco.
    
11. Per associare uno o più utilizzi PSTN (Public Switched Telephone Network) alla route vocale, fare clic  su Seleziona e scegliere un record nell'elenco dei record di utilizzo PSTN definiti per la distribuzione di VoIP aziendale.
    
    > [!NOTE]
    > Per visualizzare le proprietà di ognuno dei record di utilizzo PSTN disponibili, vedere [View PSTN usage records in Skype for Business](view-pstn-usage-records.md). > Per creare o modificare i record di utilizzo PSTN, vedere [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md)
  
12. Organizzare i record utilizzo PSTN in modo da ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia su o giù.
    
    > [!NOTE]
    > A differenza di un criterio vocale, in cui l'ordine in cui sono elencati i record di utilizzo PSTN è importante, l'ordine in cui i record di utilizzo PSTN sono elencati nella route vocale è irrilevante. È tuttavia consigliabile organizzare l'elenco in base alla frequenza di utilizzo. Ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server attraversa l'elenco dall'alto verso il basso. 
  
13. Digitare un valore nel campo **Numero convertito da testare** e fare clic su **Vai**. I risultati del test vengono visualizzati nel campo (facoltativo).
    
14. Fare **clic su OK** per salvare la route vocale.
    
    > [!IMPORTANT]
    > Ogni volta che si crea una route vocale, è necessario eseguire il **comando Commit tutto** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>Per modificare una route vocale

1. Aprire Skype for Business Server Pannello di controllo.
    
2. Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Route**.
    
3. Nella pagina **Route** utilizzare uno dei metodi seguenti per modificare una route vocale:
    
   - Fare clic sul nome di una route vocale, fare clic su **Modifica**, quindi su **Mostra dettagli**.
    
   - Fare clic sul nome di una route vocale, fare clic su **Modifica**, su **Copia**, quindi su **Incolla**. Fare clic sulla nuova copia della route vocale appena creata, fare clic su **Modifica**, quindi su **Mostra dettagli**.
    
4. Nel campo **Nome** della pagina **Modifica route vocale** digitare un nome descrittivo per la route vocale.
    
5. Nel campo **Descrizione** digitare altre informazioni descrittive per la route vocale (facoltativo).
    
6. Per specificare i formati che questa route deve includere, è possibile utilizzare lo strumento **Formato per corrispondenza** per generare un'espressione regolare oppure scrivere tale espressione manualmente.
    
   - Per utilizzare lo strumento **Formato per corrispondenza** per generare un'espressione regolare, immettere i valori come indicato di seguito. È possibile specificare due tipi di corrispondenze di formato:
    
   - **Cifre iniziali per i numeri da consentire**: immettere i valori di prefisso che la route deve includere, incluso il segno + iniziale, se necessario. Digitare, ad esempio, +425 e quindi fare clic su **Aggiungi**. Ripetere questa operazione per ogni valore di prefisso da includere nella route.
    
   - **Eccezioni**: se si desidera specificare una o più eccezioni per un valore di prefisso, evidenziare il prefisso e fare clic su **Eccezioni**. Digitare uno o più valori per i modelli di corrispondenza che non  *si desidera*  che questa route supporti. Ad esempio, per escludere i numeri che iniziano con +425237 dalla route, immettere il valore +425237 nel campo Eccezioni e quindi  fare clic su **OK**.
    
   - Per definire manualmente il criterio di corrispondenza,  fare clic su  Modifica nello strumento Crea un modello per la corrispondenza e quindi digitare un'espressione regolare di .NET Framework per specificare il modello di corrispondenza per i numeri di telefono di destinazione a cui viene applicata la route. Per informazioni dettagliate su come scrivere espressioni regolari, vedere [".NET Framework regolari"](/dotnet/standard/base-types/regular-expressions). 
    
7. Selezionare **Elimina ID chiamante** se non si desidera che l'ID del telefono che effettua la chiamata in uscita venga visualizzato al destinatario della chiamata. Se si seleziona questa opzione, è necessario specificare un **ID** chiamante alternativo che verrà visualizzato nella visualizzazione dell'ID chiamante del destinatario.
    
8. Per associare uno o più trunk PSTN (Public Switched Telephone Network) alla route vocale, fare clic su **Aggiungi** e quindi selezionare un trunk nell'elenco.
    
9. Per associare uno o più utilizzi PSTN alla route vocale, fare clic  su Seleziona e scegliere un record dall'elenco dei record di utilizzo PSTN definiti per la distribuzione VoIP aziendale locale.
    
    > [!NOTE]
    > Per visualizzare le proprietà di ognuno dei record di utilizzo PSTN disponibili, vedere [View PSTN usage records in Skype for Business](view-pstn-usage-records.md). > Per creare o modificare i record di utilizzo PSTN, vedere [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md). 
  
10. Organizzare i record utilizzo PSTN in modo da ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia su o giù.
    
    > [!NOTE]
    > A differenza di un criterio vocale in cui l'ordine in cui sono elencati i record di utilizzo PSTN è importante, l'ordine dei record di utilizzo PSTN in una route vocale è irrilevante. È tuttavia consigliabile organizzare l'elenco per frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server attraversa l'elenco dall'alto verso il basso. 
  
11. Digitare un valore nel campo **Numero convertito da testare** e fare clic su **Vai**. I risultati del test vengono visualizzati nel campo (facoltativo).
    
12. Fare clic su **OK**.
    
13. Nella pagina **Route** fare clic su **Commit** e quindi su **Salva tutto**. 
    
    > [!NOTE]
    > Ogni volta che si crea o si modifica una route vocale, è necessario eseguire il **comando Commit all** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.
  
## <a name="see-also"></a>Vedere anche

[Visualizzare i record di utilizzo PSTN in Skype for Business](view-pstn-usage-records.md)
  
[Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for Business](voice-policy-and-pstn-usage-records.md)
  
[Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for Business](voice-route-config-changes.md)