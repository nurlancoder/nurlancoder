Bunu Windsurf-da Cascade-ə (AI chat panelinə) olduğu kimi yapışdır:

---

Mənə GitHub profil repomu (github.com/nurlancoder/nurlancoder) yeniləməkdə kömək et. Bu qovluqda (workspace root) artıq bu fayllar var: `dark.svg`, `light.svg`, `README.md`, `.github/workflows/snake.yml`, `SETUP_STEPS.md`. Bunları mənim GitHub profil repoma push etməlisən.

**Kontekst və məqsəd**
Bu fayllar GitHub profilim üçün animasiyalı banner (dot-matrix portret, Floyd-Steinberg dithering ilə çəkilib), self-hosted stats kartları üçün README bloku, contribution snake GitHub Action-u və sosial badge-lərdən ibarətdir. Fayllar artıq tam hazırdır və məzmununu dəyişməyinə ehtiyac yoxdur — sadəcə repo-ya düzgün strukturda köçürüb push etməlisən.

**Addım-addım nə etməlisən**

1. `git status` və `git remote -v` ilə bu qovluğun artıq `nurlancoder/nurlancoder` repo-suna bağlı olub-olmadığını yoxla.
   - Əgər bağlı deyilsə, mənə bunu de və `git clone https://github.com/nurlancoder/nurlancoder.git` ilə ayrıca qovluğa klonla, sonra bu 5 faylı ora köçür (üzərinə yaz, `.github/workflows/` qovluq strukturunu saxla).
   - Repo GitHub-da hələ yaradılmayıbsa, mənə xəbər ver — mən əvvəlcə github.com/new-də public repo yaratmalıyam (adı dəqiq `nurlancoder` olmalıdır, "Add a README" işarəli).

2. Fayl strukturunun tam bu cür olduğunu təsdiqlə (heç bir başqa fayl silinməməli, mövcud repo məzmunu ilə konflikt yoxlanmalıdır):
   ```
   dark.svg
   light.svg
   README.md
   .github/workflows/snake.yml
   SETUP_STEPS.md
   ```

3. Əgər repo-da onsuz da fərqli məzmunlu `README.md` varsa, mənə fərqi göstər və üzərinə yazmazdan əvvəl təsdiq al — kor-koranə overwrite etmə.

4. Git əməliyyatlarını sıra ilə icra et:
   ```
   git add dark.svg light.svg README.md .github/workflows/snake.yml SETUP_STEPS.md
   git commit -m "Add animated dot-matrix GitHub banner, self-hosted stats config, and snake workflow"
   git push origin main
   ```
   - Branch adı `main` deyil, `master`-dırsa, ona uyğunlaş.
   - Push zamanı autentifikasiya soruşularsa, MƏNDƏN Personal Access Token və ya GitHub CLI login istə — token-i heç vaxt terminalda görünən şəkildə çap etmə, log-a yazma, fayla yazma.

5. Push uğurlu olduqdan sonra:
   - Mənə push olunan commit hash-ini və GitHub-dakı fayl linklərini göstər.
   - Actions tabındakı `Generate Snake Animation` workflow-nun avtomatik işə düşüb-düşmədiyini yoxlamağı mənə xatırlat (bu, `output` branch-i yaradana qədər README-də snake şəkli "broken" görünəcək — bu normaldır, sənin problemin deyil).
   - Repo-nun öz Settings → Actions → General → Workflow permissions bölməsində "Read and write permissions" aktiv olmasa, snake workflow-nun uğursuz olacağını mənə xatırlat (bunu mən özüm brauzerdən edəcəm, sən edə bilməzsən).

**Nəyi ETMƏ**
- SVG və ya README faylının içindəki məzmunu (rəng, mətn, animasiya) dəyişmə — onlar artıq final versiyadır.
- `git push --force` istifadə etmə, heç vaxt təsdiqsiz.
- Heç bir token/parolu fayla yazma və ya commit et.
- Vercel deploy və ya GitHub token yaratma addımlarını mənim əvəzimə etməyə çalışma — onlar brauzerdə OAuth/qeydiyyat tələb edir, sənin əlin çatmır. Bunun üçün mənə `SETUP_STEPS.md`-dəki 2–4-cü addımları xatırlat, vəssalam.

Əgər hər hansı addımda qeyri-müəyyənlik olsa (repo yoxdur, branch adı fərqlidir, konflikt var və s.), davam etməzdən əvvəl mənə sual ver.

---
