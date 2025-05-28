# my-proxmox-setup
Proxmox Config

## Spis Treści

- [Wprowadzenie](#wprowadzenie)
- [Wymagania wstępne](#wymagania-wstępne)
- [Krok 1: Przygotowanie iDRAC](#krok-1-przygotowanie-idrac)
- [Krok 2: Uruchomienie instalatora Proxmox](#krok-2-uruchomienie-instalatora-proxmox)
- [Krok 3: Konfiguracja dysków i strefy czasowej](#krok-3-konfiguracja-dysków-i-strefy-czasowej)
- [Krok 4: Ustawienia sieciowe](#krok-4-ustawienia-sieciowe)
- [Krok 5: Podsumowanie i zakończenie instalacji](#krok-5-podsumowanie-i-zakończenie-instalacji)
- [Dodatkowe uwagi](#dodatkowe-uwagi)

## Wymagania Wstępne

Przed rozpoczęciem instalacji upewnij się, że masz:

-   Serwer Dell PowerEdge R630 (lub inny kompatybilny serwer z iDRAC Enterprise).
-   Dostęp do sieci, do której podłączony jest iDRAC serwera.
-   Adres IP i dane logowania do interfejsu iDRAC.
-   Pobrany obraz ISO Proxmox VE (możesz go pobrać ze strony [Proxmox](https://www.proxmox.com/en/downloads/category/iso-images)).
-   Przeglądarkę internetową obsługującą HTML5 Virtual Console (zalecany Google Chrome/Firefox).
-   Zainstalowany [OpenWebStart](https://openwebstart.com/) na swoim komputerze, jeśli planujesz używać starszych aplikacji Java (np. dla iDRAC 7 lub starszych).

  ## Krok 1: Przygotowanie iDRAC

1.  **Dostęp do interfejsu iDRAC:**
    Otwórz przeglądarkę i przejdź do adresu IP swojego iDRAC. Zaloguj się danymi uwierzytelniającymi.

    ![Logowanie do iDRAC](images/01-idrac-login.png)

2.  **Uruchomienie Wirtualnej Konsoli:**
    Po zalogowaniu, znajdź i kliknij przycisk "Launch Virtual Console" (lub podobny) w panelu głównym iDRAC. Zazwyczaj uruchamia się ona jako osobne okno przeglądarki.

    ![Uruchomienie Virtual Console](images/02-launch-virtual-console.png)

3.  **Podłączenie obrazu ISO Proxmox VE:**
    W oknie wirtualnej konsoli, przejdź do sekcji **Virtual Media** (zazwyczaj w górnym menu lub ikonie). Wybierz opcję "Map CD/DVD" lub "Connect CD/DVD". Następnie wskaż pobrany plik `.iso` z Proxmox VE ze swojego komputera.

    ![Mapowanie ISO Proxmox](images/03-map-proxmox-iso.png)

4.  **Uruchomienie serwera z nośnika wirtualnego:**
    Po podłączeniu ISO, zrestartuj serwer z poziomu iDRAC (Power -> Power Cycle System (Warm Boot) lub Power Off -> Power On System). Upewnij się, że opcja bootowania z "Virtual CD/DVD" jest włączona w sekcji "Next Boot" lub w ustawieniach BIOS/UEFI.

    ![Restart serwera](images/04-idrac-power-options.png)

---

## Krok 2: Uruchomienie instalatora Proxmox

1.  **Menu startowe Proxmox:**
    Po restarcie serwera, powinieneś zobaczyć menu startowe instalatora Proxmox VE w wirtualnej konsoli. Wybierz opcję "Install Proxmox VE".

    ![Menu startowe Proxmox](images/05-proxmox-boot-menu.png)
