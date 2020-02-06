---
title: Visualizzare le informazioni sul PIN utente in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Riepilogo: visualizzare le informazioni sul PIN utente in Skype for Business Server.'
ms.openlocfilehash: 236148de5b100220731d723df3217205b258879e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818688"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Visualizzare le informazioni sul PIN utente in Skype for Business Server
 
**Riepilogo:** Visualizzare le informazioni sui PIN utente in Skype for Business Server.
  
Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Skype for Business Server con credenziali di Active Directory Domain Services (AD DS) richiede un PIN (Personal Identification Number). È possibile visualizzare le informazioni sul PIN di un utente dal pannello di controllo di Skype for Business Server.
  
> [!NOTE]
> È possibile visualizzare le informazioni sullo stato del PIN, ad esempio se il PIN è stato impostato o quando il PIN è stato modificato per l'ultima volta, ma non è possibile visualizzare il PIN corrente guardando lo stato del PIN. Se un utente ha perso il PIN, è possibile reimpostarlo seguendo le procedure descritte in [impostare un PIN per i servizi di conferenza telefonica con accesso esterno di un utente in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Per visualizzare il PIN di un utente nel pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Usare uno dei metodi seguenti per individuare un utente:
    
   - Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.
    
   - Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.
    
5. Opzionale Specificare altri criteri di ricerca per restringere i risultati:
    
   un. Fare clic su **Aggiungi filtro**.
    
   b. Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.
    
   c. Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.
    
   3D. A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.
    
    > [!TIP]
    > Per aggiungere altre clausole di ricerca alla query, fare clic su **Aggiungi filtro**. 
  
   e. Fare clic su **trova**.
    
    > [!NOTE]
    > Se il PIN è bloccato, è necessario sbloccare il PIN prima di poterlo impostare. Per sbloccare il PIN, fare clic sull'utente, fare clic su **azione**e quindi su **Sblocca PIN**. 
  
6. Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Visualizza stato PIN**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sui PIN utente tramite i cmdlet di Windows PowerShell

Puoi visualizzare le informazioni sul PIN utente usando il cmdlet Get-CsClientPinInfo. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-view-user-pin-information"></a>Per visualizzare le informazioni sul PIN dell'utente

Per visualizzare le informazioni sul PIN per un utente, digitare un comando simile a quello seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Questo restituirà informazioni simili alla seguente:

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .
  
## <a name="see-also"></a>Vedere anche

[Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[Bloccare o sbloccare un PIN utente in Skype for Business Server](lock-or-unlock-a-user-pin.md)
