<h1>Zadania do szkolenia</h1>
<a href="https://console.aws.amazon.com">Link do AWS jako root account</a><br>
<a href="https://212567597667.signin.aws.amazon.com/console">Link do "subdomeny" AWS (dla użytkowników stworzonych przez roota)</a>
<h2>Zadanie 1 - PIERWSZA USŁUGA (maszyna wirtualna)</h2>
<ol>
	<li>Zaloguj się do AWS Console (użyj linku powyżej)</li>
	<li>Przełącz się na jeden z regionów europejskich (prawy górny róg)
		<ul>
			<li>RevolveTrainingUser[1-3] wybierają Frankfurt</li>
			<li>RevolveTrainingUser[4-6] wybierają Ireland</li>	
		</ul>
	</li>
	<li>Z listy usług AWS ("Services" lewy górny róg) wybierz EC2 (sekcja "Compute")</li>
	<li>Wybierz „Instances” lub "Running instances", a następnie „Launch Instance”</li>
	<li>Dobierz konfigurację
		<ul>
			<li>Name and tags
				<ul>
					<li>W polu "Name" podaj dowolną rozpoznawalną nazwę (będzie potrzebna do indentyfikacji na liście maszyn)</li>
					<li>Kliknij szary przycisk "Next: Configure Security Group"</li>
				</ul>
			</li>
			<li>Application and OS Images (Amazon Machine Image)
				<ul>
					<li>Zaznacz "Windows"</li>
				</ul>
			</li>
			<li>Instance type
				<ul>
					<li>Znajdź i zaznacz typ/moc instancji np. "t2.medium"</li>
				</ul>
			</li>
			<li>Key pair (login)
				<ul>
					<li>Kliknij "Create a new key pair"</li>
					<li>Dowolnie nazwij klucz</li>
					<li>Kliknij przycisk "Create key pair"</li>
					<li>Zauważ, że został pobrany plik pem z kluczem (NIE ZGUB GO! Będzie za chwilę potrzebny)</li>
				</ul>
			</li>
			<li>Network settings
				<ul>
					<li>Zostaw wszystko domyślnie</li>
				</ul>
			</li>
			<li>Configure storage
				<ul>
					<li>Zostaw wszystko domyślnie</li>
				</ul>
			</li>
			<li>Advanced details
				<ul>
					<li>Zostaw wszystko domyślnie</li>
				</ul>
			</li>
			<li>Summary
				<ul>
					<li>Sprawdź wprowadzoną konfigurację</li>
					<li>Kliknij przycisk "Launch instance" (prawy dolny róg)</li>
				</ul>
			</li>
		</ul>
	</li>
	<li>Przejdź do listy instancji np. klikając w przycisk "View all instances"</li>
	<li>Zaloguj się do swojej maszyny wirtualnej
		<ul>
			<li>Znajdź i zaznacz swoją maszynę wirtualną</li>
			<li>Kliknij szary przycisk „Connect” (nad listą instancji)</li>
			<li>Wybierz zakładkę RDP Client "Get Password"</li>
			<li>Pobierz plik RDP klikając w przycisk "Download Remote Desktop File"</li>
			<li>Pobierz hasło
				<ul>					
					<li>Kliknij w szary przycisk "Get Password"</li>
					<li>Poczekaj aż odblokuje się możliwość pobrania hasła (3-5 min)</li>
					<li>Kliknij w przycisk "Choose file"</li>
					<li>Znajdź i wybierz uprzednio pobrany plik/klucz</li>
					<li>Kliknij w szary przycisk "Decrypt Password"</li>
					<li>Skopiuj hasło</li>
					<li>Zamknij okno klikając w niebieski przycisk "Close"</li>
				</ul>
			</li>
			<li>Użyj pobranego pliku RDP i hasła do zalogowania się na maszynę wirtualną</li>
			<li>Używaj maszyny wirtualnej w dowolnym celu :D</li>
		</ul>
	</li>
</ol>
<h2>ZADANIE 2 – SKALOWANIE WERTYKALNE (W GÓRĘ I W DÓŁ)</h2>
<ol>
	<li>Zaalokuj nowy adres publiczny (EIP)
		<ul>
			<li>Z listy usług AWS wybierz EC2 (prawdopodobnie już tu jesteś)</li>
			<li>Z panelu po lewej stronie wybierz "Elastic IPs" (zakładka "NETWORK & SECURITY")</li>
			<li>Kliknij pomarańczowy przycisk "Allocate Elastic IP address"</li>
			<li>Dodaj Tag o nazwie "Name" klikając w szary przycisk "Add new tag"</li>
			<li>Potwierdź zamiar klikając pomarańczowy przycisk "Allocate"</li>
			<li>Zamknij okno klikając pomarańczowy przycisk "Close"</li>
		</ul>
	</li>
	<li>Podepnij EIP do istniejącej instancji
		<ul>
			<li>Zaznacz nowoutworzony EIP</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na EIP</li>
			<li>Wybierz opcję "Associate Elastip IP address"</li>
			<li>Kliknij w textbox "Instance", znajdź i wybierz swoją instancję</li>
			<li>Zaznacz na samym dole checkbox "Allow this Elastic IP address to be reassociated"</li>
			<li>Kliknij pomarańczowy przycisk "Associate"</li>
			<li>Jeżeli jesteś zalogowany(a) przez RDP, to prawdopodobnie Cię wyloguje, ponieważ zmienił się adres IP</li>
		</ul>
	</li>
	<li>Sprawdź wydajność swojej maszyny wirtualnej
		<ul>
			<li>Pobierz i rozpakuj program CPU-Z z "https://download.cpuid.com/cpu-z/cpu-z_2.01-en.zip"</li>
			<li>Zaloguj się do maszyny wirtualnej (opis w zadaniu 1) - zauważ, że zmienił się publiczny adres IP</li>
			<li>Skopiuj i odpal plik cpuz_x64.exe</li>
			<li>Uruchom test wydajności (zakładka "Bench", przycisk "Bench CPU")</li>
			<li>Zapisz wynik testu CPU Multi Thread</li>
		</ul>
	</li>
	<li>Utwórz obraz maszyny wirtualnej (AMI)
		<ul>
			<li>Przejdź do listy instancji</li>
			<li>Zaznacz swoją instancję</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na instancję</li>
			<li>Wybierz opcję "Image and templates"->"Create Image"</li>
			<li>W polu "Image name" wpisz dowolną nazwę obrazu</li>
			<li>Kliknij przycisk "Create Image"</li>
			<li>Przejdź do listy utworzonych obrazów klikając na panelu z lewej strony "AMIs" (zakładka "Images")</li>
			<li>Poczekaj aż obraz będzie gotowy (3-5 min)</li>
			<li>Maszyna źródłowa zostanie na chwilę wyłączona, ale sama się uruchomi</li>
		</ul>
	</li>
	<li>Utwórz maszynę wirtualną z obrazu AMI
		<ul>
			<li>Przejdź do listy instancji EC2</li>
			<li>Kliknij „Launch instances”</li>
			<li>Application and OS Images (Amazon Machine Image)
				<ul>
					<li>Wybierz z lewego panelu "My AMIs"</li>
					<li>Znajdź swój nowoutworzony obraz</li>
					<li>Kliknij pomarańczowy przycisk "Select"</li>
				</ul>
			</li>
			<li>Instance type
				<ul>
					<li>Wybierz mocniejszą lub słabszą maszynę (liczba procesorów)</li>
				</ul>
			</li>
			<li>Reszta kroków jak w zadaniu 1</li>
			<li>Tym razem nie musisz tworzyć nowego pliku-klucza. Możesz wybrać istniejący.</li>
		</ul>
	</li>
	<li>Przełącz EIP (publiczny IP) między maszynami wirtualnymi
		<ul>
			<li>Przejdź do listy EIP</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na EIP</li>
			<li>Wybierz opcję "Associate Elastic IP address"</li>
			<li>Kliknij w textbox "Instance", znajdź i wybierz swoją nową (mocniejszą) instancję</li>			
			<li>Zaznacz opcję "Allow Elastic IP to be reassociated if already attached"</li>
			<li>Kliknij przycisk "Associate"</li>
		</ul>
	</li>
	<li>Sprawdź wydajność swojej nowej (mocniejszej) maszyny wirtualnej
		<ul>
			<li>Zaloguj się do maszyny przez RDP (hasło jest takie samo jak do oryginalnej maszyny)</li>
			<li>Zauważ, że plik "cpuz_x64.ex" już się tam znajduje</li>
			<li>Uruchom test wydajności (zakładka "Bench", przycisk "Bench CPU")</li>
			<li>Zapisz czas wykonania programu</li>
		</ul>
	</li>
	<li>Porównaj wyniki obu testów maszyn wirtualnych (słabszej i mocniejszej)</li>
	<li>Usuń maszyny i EIP (posprzątaj)
		<ul>
			<li>Przejdź do listy instancji</li>
			<li>Zaznacz swoje instancje</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na instancję</li>
			<li>Wybierz opcję "Instance State"->"Terminate"</li>
			<li>Potwierdź działanie klikając niebieski przycisk "Yes, terminate"</li>
		</ul>
	</li>
</ol>
<h2>(opcjonalnie) ZADANIE 2 – SKALOWANIE WERTYKALNE (bez EIP i AMI)</h2>
<ol>
	<li>Zatrzymaj maszynę wirtualną</li>
	<li>Zmień typ instancji (na mocniejszą lub słabszą)</li>	
	<li>Uruchom ponownie maszynę wirtualną</li>
	<li>Sprawdź wydajność swojej maszyny wirtualnej</li>
</ol>
<h2>ZADANIE 3 – ZAŁADUJ I UDOSTĘPNIJ PLIK</h2>
<ol>
	<li>Przygotuj pliki testowe na lokalnym komputerze
		<ul>			
			<li>Otwórz dowolną linię poleceń np. cmd/git bash/powershell z uprawnieniami administratora</li>
			<li>Wygeneruj plik testowy korzystając z <i>fsutil file createnew testfile 100000000</i></li>
			<li>Pobierz (jeżeli nie masz) dowolny manager pobierań (np. <a href="https://sourceforge.net/projects/urlget/files/latest/download">uget</a>)</li>
		</ul>
	</li>
	<li>Przygotuj usługę S3
		<ul>
			<li>Z listy usług AWS wybierz S3 (kategoria "Storage")</li>
			<li>Kliknij w przycisk "Create Bucket" w prawym górnym rogu</li>
			<li>Skonfiguruj bucket
				<ol>
					<li>General configuration
						<ul>
							<li>W polu "Bucket name" podaj unikalną (na skalę AWS) nazwę bucketa</li>
							<li>Wybierz jakiś odległy region w Asia Pacific (Sydney lub Seul)</li>
						</ul>
					</li>
					<li>Object Ownership
						<ul>
							<li>Zaznacz checkbox "ACLs enabled"</li>
						</ul>
					</li>
					<li>Block Public Access settings for this bucket
						<ul>
							<li>Odznacz checkbox "Block all public access"</li>
							<li>Zaznacz zgodę "I acknowledge that the current settings might result in this bucket and the objects within becoming public."</li>
						</ul>
					</li>												<li>Kliknij pomarańczowy przycisk "Create bucket"</li>
				</ol>
			</li>			
		</ul>
	</li>
	<li>Wgraj plik testowy do usługi S3 i udostępnij
		<ul>
			<li>Otwórz bucket (kliknij w jego nazwę na liście)</li>
			<li>Kliknij w pomarańczowy przycisk "Upload" w prawym górnym rogu</li>
			<ol>
				<li>Select files
					<ul>
						<li>Kliknij "Add files"</li>
						<li>Wybierz plik "testfile"</li>
					</ul>
				</li>
				<li>Rozwiń zakładkę "Permissions"
					<ul>
						<li>Zaznacz w opcjach "Predefined ACLs" radiobutton "Grant public-read access"</li>
						<li>Zaznacz zgodę "I understand the risk of granting public-read access to the specified objects."</li>
					</ul>
				<li>Kliknij pomarańczowy przycisk "Upload" w prawym dolnym rogu</li>
				<li>Upload: status
					<ul>
						<li>Poczekaj aż plik zostanie załadowany</li>
						<li>Kliknij pomarańczowy przycisk "Close" w prawym górnym rogu</li>
					</ul>
				</li>
			</ol>
		</ul>
	</li>
	<li>Przeprowadź test czasu odpowiedzi
		<ul>			
			<li>Kliknij plik w bucket'cie</li>
			<li>Skopiuj link do pliku ("Object URL")</li>
			<li>Wydziel z linku domenę (np. s3.ap-northeast-2.amazonaws.com)</li>
			<li>Otwórz na komputerze lokalnym command line (CMD)</li>
			<li>Odpytaj host bucketa narzędziem ping (np. ping s3-website-eu-west-1.amazonaws.com)</li>
			<li>Zapisz czas odpowiedzi</li>
		</ul>
	</li>
	<li>Przeprowadź test prędkości pobierania
		<ul>
			<li>Przygotuj link do pliku (NIE samej domeny)</li>
			<li>Pobierz kilka razy plik za pomocą dowolnego managera pobierań (np. <a href="https://sourceforge.net/projects/urlget/files/latest/download">uget</a>)</li>
			<li>Zapisz najniższy czas pobierania</li>
		</ul>
	</li>
</ol>
<h2>ZADANIE 4 – ROZPROSZYĆ PLIK PO CAŁYM ŚWIECIE</h2>
<ol>
	<li>Przygotuj usługę CloudFront
		<ul>
			<li>Wybierz usługę CloudFront (kategoria "Networking & Content Delivery")</li>
			<li>Kliknij w pomarańczowy przycisk „Create Distribution”</li>
			<li>W polu "Origin domain" wybierz bucket S3 (utworzony w poprzednim zadaniu)</li>
			<li>W zakładce "Settings" ustaw "Price class" jako "Use only North America and Europe"</li>
			<li>Kliknij w pomarańczowy przycisk „Create Distribution” w prawym dolnym rogu</li>	
		</ul>
	</li>
	<li>(Deploying) Odczekaj minimum 15 minut (przerwa na kawę)</li>
	<li>Przeprowadź test czasu odpowiedzi
		<ul>
			<li>Znajdź i skopiuj adres hosta CloudFront ("Domain Name")</li>
			<li>Otwórz 'CMD'</li>
			<li>Odpytaj host CloudFronta narzędziem ping (np. ping d30wp07u6aouly.cloudfront.net)</li>
			<li>Zapisz czas odpowiedzi</li>
		</ul>
	</li>
	<li>Przeprowadź test prędkości pobierania
		<ul>
			<li>Doklej do adresu hosta dystrybucji CloudFront nazwę pliku (bez nazwy bucketa S3)</li>
			<li>Pobierz kilka razy plik za pomocą managera pobierań</li>
			<li>Zapisz średni czas pobierania</li>
		</ul>
	</li>
</ol>
<h2>ZADANIE 5 – SECURITY GROUPS - FIREWALL</h2>
<ol>
	<li>Utwórz instancję EC2 (Linux)</li>
	<li>Utwórz puste Security Group (Firewall)
		<ul>
			<li>Przejdź do usługi EC2</li>
			<li>Z panelu po lewej stronie wybierz "Security Groups" (zakładka "Network & Security")</li>
			<li>Kliknij przycisk "Create Security Group"</li>
			<li>Nadaj nazwę oraz opis (niestety również wymagany)</li>
			<li>Kliknij niebieski przycisk "Create"</li>
			<li>Puste Security Group nie przyjmuje żadnych połączeń</li>
		</ul>
	</li>
	<li>Przypisz nowe Security Group do EC2
		<ul>
			<li>Przejdź do listy instancji</li>
			<li>Zaznacz swoją (jedyną) instancję</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na instancję</li>
			<li>Wybierz opcję "Networking"->"Change Security Groups"</li>
			<li>Odznacz domyślne Security Group</li>
			<li>Zaznacz nowoutworzone Security Group</li>
			<li>Kliknij przycisk "Assign Security Groups"</li>
		</ul>
	</li>
	<li>Zacznij wysyłać pakiety ICMP do EC2 (ping -t) do nowoutworzonej instancji EC2</li>
	<li>Skonfiguruj Security Group
		<ul>
			<li>Znajdź i zaznacz nowoutworzone Security Group</li>
			<li>Kliknij szary przycisk "Actions" lub kliknij prawym przyciskiem myszyny na Security Group</li>
			<li>Wybierz opcję "Edit inbound rules" lub kliknij "Edit" w zakładce "Inbound" w panelu na dole</li>
			<li>Wybierz Type "All ICMP"</li>
			<li>Wybierz Source "My IP" (zostanie wykorzystany IP sieci Revolve)</li>
			<li>Kliknij niebieski przycisk "Save"</li>
		</ul>
	</li>
	<li>Sprawdź czy przypisanie nowych zasad przepuszcza pakiety ICMP (propagacja odebrania dostępu w SG trwa 5 min, restart vm i nadanie praw daje natychmiastowy efekt)</li>
</ol>
