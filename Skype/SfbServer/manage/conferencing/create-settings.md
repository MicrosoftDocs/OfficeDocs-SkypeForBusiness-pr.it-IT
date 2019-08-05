---
title: Creare impostazioni di configurazione delle riunioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Riepilogo: informazioni su come creare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: 3d4f986b850b309d50967da9126b8b4eea08a166
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194481"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>Creare impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
Puoi creare le impostazioni di configurazione delle riunioni usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Creare impostazioni di configurazione delle riunioni tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **Configurazione riunione**.
    
4. Nella pagina **Configurazione riunione** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
    - Per creare un criterio a livello di sito, fare clic su **configurazione sito**. Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per il quale si desidera definire le impostazioni di partecipazione alle riunioni. Nell'elenco dei siti risultante fare clic sul sito desiderato e quindi fare clic su **OK**.
    
    - Per creare criteri a livello di pool, fare clic su **Configurazione pool**. Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio pool per cui si desidera definire le impostazioni di partecipazione alle riunioni. Nell'elenco dei servizi risultante fare clic sul pool desiderato e quindi fare clic su **OK**.
    
5. Per instradare i partecipanti che effettuano la chiamata tramite la rete PSTN (Public Switched Telephone Network) nella sala di attesa, deselezionare la casella di controllo **Ignora chiamate PSTN** . Per impostazione predefinita, i partecipanti che effettuano la chiamata dalla rete PSTN accedono direttamente alla riunione.
    
6. Per configurare chi può essere un relatore nella riunione, in **designa come**relatore eseguire una delle operazioni seguenti:
    
   - Per non consentire a utenti diversi dall'organizzatore di essere relatori, fare clic su **nessuno**.
    
   - Per consentire solo ai partecipanti membri dell'organizzazione di essere relatori, fare clic su **società**. Questa è l'impostazione predefinita.
    
   - Per consentire a tutti i partecipanti di essere un relatore, fare clic su **tutti**.
    
7. Per fare in modo che l'organizzatore selezioni un tipo di conferenza durante la programmazione di una riunione, deselezionare la casella **di controllo tipo di conferenza assegnata per impostazione predefinita** . Per impostazione predefinita, il tipo di conferenza viene assegnato automaticamente.
    
8. Per impedire l'ammissione automatica degli utenti anonimi (non autenticati), deselezionare la casella **di controllo Ammetti gli utenti anonimi per impostazione predefinita** . Per impostazione predefinita, gli utenti anonimi vengono ammessi automaticamente alle riunioni.
    
9. Per personalizzare l'invito alla riunione inviato ai partecipanti, eseguire le operazioni seguenti. Tieni presente che la lunghezza massima per gli URL e il testo del piè di pagina personalizzato è 1KB. Ad eccezione dell' **URL della Guida**, se non si specifica un valore per le personalizzazioni, questi non verranno inclusi nella riunione. Se non si include un URL della Guida personalizzato, l'URL della Guida predefinito per Skype for business verrà visualizzato nell'invito. 
    
   - Per personalizzare il logo visualizzato nell'invito alla riunione, in **URL logo**immettere la posizione del logo. Il logo deve essere un'immagine GIF o JPG con una dimensione di 188 di 30 pixel. 
    
   - Per personalizzare il testo della Guida visualizzato nell'invito alla riunione, in **URL della Guida**immettere la posizione del testo della guida.
    
   - Per personalizzare il testo legale visualizzato nell'invito alla riunione, in **URL di testo legale**immettere la posizione del testo legale.
    
   - Per personalizzare il testo del piè di pagina visualizzato nell'invito alla riunione, nel **testo del piè**di pagina personalizzato immettere il testo.
    
10. Fare clic su **Commit**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Creare impostazioni di configurazione delle riunioni con Skype for Business Server Management Shell

Per creare le impostazioni di configurazione della riunione, usare il cmdlet **New-CsMeetingConfiguration** .
  
Il comando seguente crea un nuovo set di impostazioni di configurazione delle riunioni per il sito Redmond:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, le nuove impostazioni di configurazione della riunione utilizzeranno i valori predefiniti per tutte le relative proprietà.
  
Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati. Ad esempio, per creare una raccolta di impostazioni di configurazione della riunione che, per impostazione predefinita, ammettono tutti a una riunione come relatore usare un comando come questo:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Più valori di proprietà possono essere impostati includendo più parametri. Ad esempio, il comando seguente ammette tutti i partecipanti a una riunione come relatore e costringe anche gli utenti PSTN ad attendere nella sala di attesa finché non vengono formalmente ammessi alla riunione:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Per altre informazioni, incluso un elenco completo dei parametri, vedere [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).
  

