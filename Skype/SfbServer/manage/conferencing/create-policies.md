---
title: Creare criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Riepilogo: informazioni su come creare criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 323a50ab779e772ca6149dc4c151f9d42d55df66
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195544"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a>Creare criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare criteri di conferenza in Skype for Business Server.
  
Puoi creare criteri di conferenza usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Creare criteri di conferenza tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.
    
4. Fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
   - Per creare un criterio a livello di utente, fare clic su **criteri utente**. In **nome**digitare un nome descrittivo per il criterio in **nuovi criteri di conferenza**.
    
   - Per creare un criterio a livello di sito, fare clic su **criteri sito**. Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per cui si vuole creare un criterio. Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.
    
     > [!NOTE]
     > Il nome del sito diventa il nome del criterio di conferenza; non è possibile modificarlo. 
  
5. In **Descrizione**Digitare una descrizione per il criterio.
    
6. In **Criteri organizzazione**, in **dimensioni massime riunione**, digitare il numero massimo di utenti che si vuole consentire a una riunione. Per impostazione predefinita, la dimensione massima della riunione è 250.
    
7. Per impedire agli utenti di invitare utenti anonimi alle riunioni, deselezionare la casella **di controllo Consenti ai partecipanti di invitare utenti anonimi** . Gli utenti anonimi sono utenti che non hanno credenziali nei servizi di dominio Active Directory dell'organizzazione e che, pertanto, non vengono autenticati. Per impostazione predefinita, gli utenti possono invitare utenti anonimi alle riunioni.
    
8. In **registrazione**eseguire una delle operazioni seguenti:
    
   - Per impedire ai partecipanti di registrare riunioni, fare clic su **nessuno**. Questa è l'impostazione predefinita.
    
   - Per consentire ai partecipanti di registrare riunioni, fare clic su **Abilita registrazione**.
    
9. Per consentire ai partecipanti esterni di registrare le riunioni, selezionare la casella **di controllo Consenti ai partecipanti federati e anonimi di registrare** . Il valore predefinito è impedire ai partecipanti esterni di registrare riunioni.
    
10. In **audio/video**eseguire una delle operazioni seguenti:
    
    - Per evitare l'uso di audio e video, fare clic su **nessuno**.
    
    - Per consentire l'uso di audio ma non video, fare clic su **Abilita audio IP**.
    
    - Per consentire l'uso di audio e video, fare clic su **Abilita audio/video IP**. Questa è l'impostazione predefinita.
    
11. Se si è scelto di consentire l'uso di audio in **audio/video**, eseguire le operazioni seguenti:
    
    - Per impedire agli utenti di partecipare alla riunione effettuando la chiamata, deselezionare la casella di controllo **Abilita conferenza telefonica con accesso esterno PSTN** . Per impostazione predefinita, gli utenti possono eseguire la chiamata alle riunioni tramite la rete PSTN (Public Switched Telephone Network).
    
    - Se si consente agli utenti di accedere alle riunioni e si vuole consentire agli utenti non autenticati (anonimi) di partecipare a una riunione con chiamate in uscita, selezionare la casella **di controllo Consenti ai partecipanti anonimi di** effettuare la chiamata in uscita. Con la chiamata in uscita, il server della conferenza chiama l'utente e l'utente risponde al telefono per partecipare alla riunione. Per impostazione predefinita, gli utenti anonimi non possono partecipare a una riunione tramite chiamata in uscita.
    
12. Se si è scelto di consentire l'uso di video in **audio/video**, selezionare **Consenti più flussi video**.
    
13. In **collaborazione con i dati**eseguire una delle operazioni seguenti:
    
    - Per impedire la collaborazione con i dati, fare clic su **nessuno**.
    
    - Per consentire la collaborazione con i dati, fare clic su **Abilita collaborazione dati**. Questa è l'impostazione predefinita.
    
14. Se si è scelto di consentire la collaborazione ai dati in collaborazione con i **dati**, eseguire le operazioni seguenti:
    
    - Per impedire i download esterni, deselezionare la casella **di controllo Consenti ai partecipanti federati e anonimi di scaricare contenuto** . Per impostazione predefinita, gli utenti esterni possono scaricare contenuto.
    
    - Per impedire i trasferimenti di file, deselezionare la casella **di controllo Consenti ai partecipanti di trasferire file** . Per impostazione predefinita, gli utenti possono trasferire file.
    
    - Per evitare l'uso di annotazioni, deselezionare la casella di controllo **Abilita** annotazioni. Per l'uso delle annotazioni nelle presentazioni di PowerPoint condivise, deselezionare l'abilitazione delle annotazioni di **PowerPoint**. Per impostazione predefinita, le annotazioni sono consentite.
    
    - Per evitare l'uso dei sondaggi, deselezionare la casella di controllo **Abilita sondaggi** . Per impostazione predefinita, i sondaggi sono consentiti.
    
15. In **condivisione applicazioni**eseguire una delle operazioni seguenti:
    
    - Per impedire l'uso della condivisione delle applicazioni, fare clic su **Disattiva condivisione applicazioni**.
    
    - Per consentire l'uso della condivisione delle applicazioni, fare clic su **Abilita condivisione applicazioni**. Questa è l'impostazione predefinita.
    
16. Se si è scelto di consentire la condivisione delle applicazioni nella **condivisione delle applicazioni**, eseguire le operazioni seguenti:
    
    - Per evitare che i partecipanti alla riunione prendano il controllo della condivisione delle applicazioni, deselezionare la casella **di controllo Consenti ai partecipanti di assumere controlli** . Per impostazione predefinita, i partecipanti possono assumere il controllo della condivisione delle applicazioni.
    
    - Se si è scelto di consentire ai partecipanti alla riunione di assumere il controllo della condivisione delle applicazioni, selezionare la casella di controllo **Consenti ai partecipanti federati e anonimi di assumere controlli** per consentire agli utenti esterni di assumere il controllo della condivisione delle applicazioni. Per impostazione predefinita, gli utenti esterni non possono assumere il controllo della condivisione delle applicazioni.
    
17. In **criteri partecipante**eseguire una delle operazioni seguenti:
    
    - Per impedire sia la condivisione delle applicazioni che la condivisione desktop, fare clic su **Disattiva condivisione applicazioni e desktop**.
    
    - Per consentire la condivisione delle applicazioni, ma non la condivisione desktop, fare clic su **Abilita condivisione applicazioni**.
    
    - Per consentire la condivisione delle applicazioni e la condivisione desktop, fare clic su **Abilita condivisione applicazioni e desktop**. Questa è l'impostazione predefinita.
    
18. Per impedire i trasferimenti di file peer-to-peer, deselezionare la casella di controllo **Consenti trasferimento file peer-to-** peer. Per impostazione predefinita, i trasferimenti di file peer-to-peer sono consentiti.
    
19. Per consentire la registrazione peer-to-peer, selezionare la casella di controllo **Abilita registrazione peer-to-peer** . Per impostazione predefinita, la registrazione peer-to-peer non è consentita.
    
20. Per consentire ai partecipanti di partecipare con più flussi video, selezionare la casella **di controllo Consenti ai partecipanti di partecipare con più flussi video** . Per impostazione predefinita, sono consentiti più flussi video.
    
21. Fare clic su **Commit**.
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Creare criteri di conferenza tramite Skype for Business Server Management Shell

Per creare criteri di conferenza, usare il cmdlet **New-CsConferencingPolicy** .
  
L'esempio seguente crea un nuovo criterio di conferenza con Identity SalesConferencingPolicy. Questo criterio utilizzerà tutti i valori predefiniti per i criteri di conferenza tranne uno: MaxMeetingSize. In questo esempio, la dimensione massima per una riunione verrà impostata su 50 anziché sul valore predefinito di 250:
  
```
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

Per altre informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, vedere [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).
  

