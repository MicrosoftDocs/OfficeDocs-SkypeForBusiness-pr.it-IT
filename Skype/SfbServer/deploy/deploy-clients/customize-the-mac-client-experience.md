---
title: Personalizzare l'esperienza del client Mac in Skype for business
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: In questo articolo vengono illustrate le preferenze client e le impostazioni predefinite disponibili per il client Skype for business per Mac e come modificarle dall'esterno dell'app.
ms.openlocfilehash: 582c9a1b12cf6dd687eff5fe0cb829e1aca98df7
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002656"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a>Personalizzare l'esperienza del client Mac in Skype for business
 
In questo articolo vengono illustrate le preferenze client e le impostazioni predefinite disponibili per il client Skype for business per Mac e come modificarle dall'esterno dell'app.
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a>Impostazioni delle preferenze client Skype for business per Mac

Alcune caratteristiche e comportamenti disponibili per i client Skype for business per Mac sono determinati dalle impostazioni delle preferenze nel client. Le preferenze di Skype for business per Mac si trovano in un file che si trova in un Mac che ha installato il client Skype for business situato nel percorso seguente: 
  
 **~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**
  
Per impostare queste preferenze, accedere a una richiesta di terminale nel Mac del client e, se necessario, immettere i comandi di default per scrivere le chiavi com. Microsoft. SkypeForBusiness usando i tasti di preferenza descritti nella tabella seguente.
  
**Tasti preferenza client**


| Chiave | Tipo | Valore | Descrizione |
|:-----|:-----|:-----|:-----|
|autoDetectAutoDicoveryURLs    |Bool    |0 = configurazione manuale del server  <br/> 1 = rilevamento automatico del server (impostazione predefinita)    |Specifica come Skype for business identifica il trasporto e il server da usare durante l'accesso. Se si abilita questa impostazione per i criteri, è necessario specificare **internalAutoDiscoveryURL** e **externalAutoDiscoveryURL**.   |
|internalAutoDiscoveryURL    |Stringa    |URL di individuazione automatica completo    |URL di individuazione automatica interno    |
|externalAutoDiscoveryURL    |Stringa    |URL di individuazione automatica completo    |URL di individuazione automatica esterna    |
|httpProxyDomain    |Stringa    ||Dominio proxy HTTP    |
|httpProxyUserName    |Stringa    ||Nome utente proxy HTTP    |
|httpProxyPassword    |Stringa    ||Password proxy HTTP    |
|trustedDomainList    |Matrice    ||Elenco di domini attendibili per i reindirizzamenti HTTP.    |
|autoAcceptTimeout    |Numero    |300 (impostazione predefinita)    |Timeout di accettazione automatica per gli utenti senza cronologia delle conversazioni sul lato server.    |
|warnWhenUnknownLocationForE911    |Bool    |0 = disabilitato  <br/> 1 = abilitato    |Avvisa l'utente quando compone un numero di emergenza da un percorso sconosciuto.    |
|sipAddress    |Stringa    ||Indirizzo SIP (posta elettronica) usato per accedere a Skype for business.    |
|userName    |Stringa    ||L'UPN (nomeutente) usato per accedere a Skype for business.    |
|userNameInAdvancedOnly    |Bool    |0 = Visualizza il campo nome utente nella schermata di accesso principale e nella finestra di dialogo Proprietà avanzate  <br/> 1 = visualizzare il campo nome utente solo nella finestra di dialogo Proprietà avanzate (impostazione predefinita)    |Specificare la posizione in cui viene visualizzato il campo nome utente durante l'accesso.    |
   
### <a name="usage-examples"></a>Esempi di utilizzo

Per aggiungere un singolo dominio (Contoso.com) all'elenco di domini attendibili, è possibile usare la chiave trustedDomainList come illustrato:
  
i valori predefiniti scrivono com. Microsoft. SkypeForBusiness trustedDomainList-array-add "Contoso.com"
  
Per aggiungere diversi domini all'elenco di domini attendibili, è possibile usare la chiave trustedDomainList come illustrato:
  
i valori predefiniti scrivono com. Microsoft. SkypeForBusiness trustedDomainList-array-add "sfb.com" "abc.com" "test.org"
  
### <a name="sample-unedited-settings"></a>Esempio di impostazioni non modificate

Per riferimento, ecco un file di impostazioni di esempio che usa solo le impostazioni predefinite: 
  
```console
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
