# Building
```powershell
dotnet build --configuration Release
```


# Silent setup
Launch elevated PowerShell or CMD and paste modified command
```powershell
msiexec /qn /i "bin\Release\mingw.msi"
```


# Updating Mingw

- Install MSYS2 from https://www.msys2.org/
- Run MSYS2 after installation (launch MSYS2 terminal)
- Download latest versions using commands below (ucrt64, mingw64, mingw32):

  - Updating MSYS2 ucrt64
  ```bash
  pacman -S mingw-w64-ucrt-x86_64-gcc
  ```

  - Updating MSYS2 mingw64
  ```bash
  pacman -S mingw-w64-x86_64-gcc
  ```

  - Updating MSYS2 mingw32
  ```bash
  pacman -S mingw-w64-i686-gcc
  ```

- Change `<Files>` tag in `mingw.wxs` to your MSYS2 install folder:
```xml
        <Files Include="c:\msys64\ucrt64\**"></Files>
        <Files Include="c:\msys64\mingw64\**"></Files>
        <Files Include="c:\msys64\mingw32\**"></Files>
```

# MINGW64 (MSVCRT) vs UCRT64 (UCRT)
More info about MSYS2 environments https://www.msys2.org/docs/environments/