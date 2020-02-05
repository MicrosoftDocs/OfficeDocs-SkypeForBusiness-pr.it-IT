---
title: Creare o modificare una route vocale in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Riepilogo: informazioni su come creare o modificare una route vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: 8732a07e835e6888efbc132da8dc99a0b4263f29
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767799"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Creare o modificare una route vocale in Skype for business
 
**Riepilogo:** Informazioni su come creare o modificare una route vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Per creare una route vocale tramite il pannello di controllo di Skype for Business Server

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **routing vocale**.
    
4. Fare clic su **Route**.
    
5. Fare clic su **nuovo** per visualizzare la finestra di dialogo **nuova route vocale** .
    
6. In **nome**Digitare un nome descrittivo per la route vocale.
    
7. Opzionale In **Descrizione**digitare altre informazioni descrittive per la route vocale.
    
8. Per specificare i motivi per cui si vuole che questa route venga adattata, è possibile usare lo strumento **Crea un modello per abbinarlo** per generare un'espressione regolare o scrivere manualmente l'espressione regolare.
    
   - Per usare lo strumento **Crea un motivo per** creare un'espressione regolare, immettere i valori come indicato di seguito. È possibile specificare due tipi di criteri di corrispondenza:
    
   - **Cifre iniziali per i numeri che si desidera consentire**: immettere i valori di prefisso che questa route deve contenere (incluso il + iniziale, se necessario). Ad esempio, digitare + 425 e quindi fare clic su **Aggiungi**. Ripetere questa operazione per ogni valore di prefisso che si vuole includere nella route.
    
   - **Eccezioni**: se si desidera specificare una o più eccezioni per un valore di prefisso, evidenziare il prefisso e fare clic su **eccezioni**. Digitare uno o più valori per i criteri di corrispondenza che *non* si vuole includere in questa route. Ad esempio, per escludere i numeri che iniziano con + 425237 dalla Route, immettere il valore + 425237 nel campo **eccezioni** e quindi fare clic su **OK**.
    
   - Per definire il modello di corrispondenza manualmente, fare clic su **modifica** nello strumento Crea modello in modo che **corrisponda** e quindi digitare un'espressione regolare di .NET Framework per specificare il modello di corrispondenza per i numeri di telefono di destinazione a cui è applicata la route. Per informazioni dettagliate su come scrivere espressioni regolari, vedere ["espressioni regolari di .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
9. Selezionare **Elimina ID chiamante** se non si vuole che l'ID del telefono che effettua la chiamata in uscita venga visualizzato nel destinatario della chiamata. Se si seleziona questa opzione, è necessario specificare un **ID chiamante alternativo** che verrà visualizzato nella visualizzazione ID chiamante del destinatario.
    
10. Per associare uno o più Trunks alla route vocale, fare clic su **Aggiungi** e quindi selezionare un trunk nell'elenco.
    
11. Per associare uno o più usi PSTN (Public Switched Telephone Network) alla route vocale, fare clic su **Seleziona** e scegliere un record dall'elenco dei record di utilizzo PSTN definiti per la distribuzione vocale aziendale.
    
    > [!NOTE]
    > Per visualizzare le proprietà di ognuno dei record di utilizzo PSTN disponibili, vedere [visualizzare i record di utilizzo PSTN in Skype for business](view-pstn-usage-records.md). > per creare o modificare i record di utilizzo PSTN, vedere [creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business](voice-policy-and-pstn-usage-records.md)
  
12. Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia verso l'alto o verso il basso.
    
    > [!NOTE]
    > A differenza di un criterio vocale, in cui l'ordine in cui sono elencati i record di utilizzo PSTN è importante, l'ordine in cui i record di utilizzo PSTN sono elencati nella route vocale è irrilevante. Tuttavia, ti consigliamo di organizzare l'elenco in base alla frequenza di utilizzo. Ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server attraversa l'elenco dall'alto verso il basso). 
  
13. Opzionale Digitare un valore nel campo **immettere un numero tradotto in test** e fare clic su **Vai**. I risultati del test vengono visualizzati sotto il campo.
    
14. Fare clic su **OK** per salvare la route vocale.
    
    > [!IMPORTANT]
    > Ogni volta che si crea una route vocale, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>Per modificare una route vocale

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **instrada**.
    
3. Nella pagina **Route** usare uno dei metodi seguenti per modificare una route vocale:
    
   - Fare clic sul nome di una route vocale, scegliere **modifica**e quindi fare clic su **Mostra dettagli**.
    
   - Fare clic sul nome di una route vocale, scegliere **modifica**, fare clic su **copia**e quindi su **Incolla**. Fare clic sulla nuova copia della route vocale appena creata, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
4. Nel campo **nome** della pagina **modifica route vocale** digitare un nome descrittivo per la route vocale.
    
5. Opzionale Nel campo **Descrizione** digitare altre informazioni descrittive per la route vocale.
    
6. Per specificare i motivi per cui si vuole che questa route sia adatta, è possibile usare lo strumento **Crea un modello per abbinarlo** per generare un'espressione regolare o scrivere manualmente l'espressione regolare.
    
   - Per usare lo strumento **Crea un motivo per** creare un'espressione regolare, immettere i valori come indicato di seguito. È possibile specificare due tipi di criteri di corrispondenza:
    
   - **Cifre iniziali per i numeri che si desidera consentire**: immettere i valori di prefisso che questa route deve contenere (incluso il + iniziale, se necessario). Ad esempio, digitare + 425 e quindi fare clic su **Aggiungi**. Ripetere questa operazione per ogni valore di prefisso che si vuole includere nella route.
    
   - **Eccezioni**: se si desidera specificare una o più eccezioni per un valore di prefisso, evidenziare il prefisso e fare clic su **eccezioni**. Digitare uno o più valori per i criteri di corrispondenza che *non* si vuole includere in questa route. Ad esempio, per escludere i numeri che iniziano con + 425237 dalla Route, immettere il valore + 425237 nel campo **eccezioni** e quindi fare clic su **OK**.
    
   - Per definire il modello di corrispondenza manualmente, fare clic su **modifica** nello strumento Crea modello in modo che **corrisponda** e quindi digitare un'espressione regolare di .NET Framework per specificare il modello di corrispondenza per i numeri di telefono di destinazione a cui è applicata la route. Per informazioni dettagliate su come scrivere espressioni regolari, vedere ["espressioni regolari di .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
7. Selezionare **Elimina ID chiamante** se non si vuole che l'ID del telefono che sta effettuando la chiamata in uscita venga visualizzato nel destinatario della chiamata. Se si seleziona questa opzione, è necessario specificare un **ID chiamante alternativo** che verrà visualizzato nella visualizzazione ID chiamante del destinatario.
    
8. Per associare uno o più Trunks PSTN (Public Switched Telephone Network) alla route vocale, fare clic su **Aggiungi**e quindi selezionare un trunk nell'elenco.
    
9. Per associare uno o più usi PSTN alla route vocale, fare clic su **Seleziona** e scegliere un record dall'elenco dei record di utilizzo PSTN definiti per la distribuzione vocale aziendale.
    
    > [!NOTE]
    > Per visualizzare le proprietà di ognuno dei record di utilizzo PSTN disponibili, vedere [visualizzare i record di utilizzo PSTN in Skype for business](view-pstn-usage-records.md). > per creare o modificare i record di utilizzo PSTN, vedere [creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business](voice-policy-and-pstn-usage-records.md). 
  
10. Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia verso l'alto o verso il basso.
    
    > [!NOTE]
    > A differenza di un criterio vocale in cui l'ordine in cui sono elencati i record di utilizzo PSTN è importante, l'ordine dei record di utilizzo PSTN in una route vocale non è significativo. Tuttavia, ti consigliamo di organizzare l'elenco in base alla frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server attraversa l'elenco dall'alto verso il basso). 
  
11. Opzionale Digitare un valore nel campo **immettere un numero tradotto in test** e fare clic su **Vai**. I risultati del test vengono visualizzati sotto il campo.
    
12. Fare clic su **OK**.
    
13. Nella pagina **Route** fare clic su **commit**e quindi su **Commit all**. 
    
    > [!NOTE]
    > Ogni volta che si crea o si modifica una route vocale, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.
  
## <a name="see-also"></a>Vedere anche

[Visualizzare i record di utilizzo PSTN in Skype for business](view-pstn-usage-records.md)
  
[Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business](voice-policy-and-pstn-usage-records.md)
  
[Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business](voice-route-config-changes.md)

