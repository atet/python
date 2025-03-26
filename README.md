# [atet](https://github.com/atet) / [**_python_**](https://github.com/atet/python/blob/main/README.md#atet--python)

[![.img/python_logo.png](.img/python_logo.png)](#nolink)

# Setup a Python Environment in One Click!

You are all in for a treat: It used to be **extremely** frustrating to set up a web application development environment years ago, but now you can do it in a single command!

In <10 minutes, we will:
- Set up a self-contained Python installation with Docker
- Tour the Jupyter development environment and learn some basics
- Create a simple web-based application and deploy it on your web browser

*I developed this tutorial on Windows 10; Windows 11 and MacOS should be very similar steps*

----------------------------------------------------------------------------

## Docker on Windows Subsystem for Linux

1. In Windows 10 & 11, you'll need Windows Subsystem for Linux (WSL) an easy install from the Microsoft Store these days (just look up and install "Ubuntu" there)
    - If you need more details, you can follow my WSL tutorial here: [https://github.com/atet/wsl](https://github.com/atet/wsl?tab=readme-ov-file#atet--wsl)
    - MacOS has a command line terminal which uses similar syntax
2. Docker Engine allows us to easily deploy self-contained (i.e., "containerized") environments in WSL; just follow the three simple commands here: [Install and Test Installation](https://github.com/atet/wsl?tab=readme-ov-file#4-cli-docker)

----------------------------------------------------------------------------

## Python and JupyterLab Development Environment

3. Copy and paste this into your terminal to download (~1.6 GB) and start JupyterLab:

```bash
$ docker run \
  -dit \
  -p 8888:8888 \
  -p 8501:8501 \
  -e JUPYTER_TOKEN="token" \
  --name jupyterlab \
  --hostname jupyterlab \
  quay.io/jupyter/minimal-notebook:latest
```

4. From that one, *maybe a couple*, clicks, JupyterLab will now be running in the background and you can access it by navigating on your web browser to `http://localhost:8888`

----------------------------------------------------------------------------

## Tour of JupyterLab and Jupyter Notebook

5. Log into JupyterLab using the access token: "`token`"
6. The Launcher has three important tiles well use in this tutorial: 
   - **Notebook/Python 3 (ipykernel)**
   - **Other/Python File**
   - **Other/Terminal**
7. Click on **Notebook/Python 3 (ipykernel)**
8. Type `x = "hello"; y = "world"` and press `SHIFT+ENTER`
9. Type `print(x, y)` and press `SHIFT+ENTER`

```
hello world
```

Looks like your Python environment is up and running!

----------------------------------------------------------------------------

## Python Basics in Notebook and Script Formats

Jupyter Notebooks use and "interactive" approach to programming where you execute line-by-line to assess results as you get them but we will use a Python script here to run everything at once.

10. Open a new tab by clicking on the "+" symbol on the top tab bar
11. Select **Other/Python File**
12. Copy and paste the following into the file and press `CTRL+S` to save as "`untitled.py`"

```python
x = "world"; y = "hello"
print(x, y)
```

13. Open another tab and select **Other/Terminal**
14. In the terminal, execute the script by running:

```bash
$ python untitled.py 
```

----------------------------------------------------------------------------

## Installing Streamlit Web Development Framework

15. In the terminal, execute the following to install Streamlit (will download ~100 MB of dependencies):

```bash
$ pip install streamlit
```

----------------------------------------------------------------------------

## Deploying a Web-Based Application

16. Make a new file named `app.py`
17. Copy and paste the following into the file and save:

```python
import streamlit as st

st.write("Hello World!")
```

18. In the terminal, run the following:

```bash
$ streamlit run app.py
```

19. In your web browser, navigate to `http://localhost:8501`

There you have it, your deployed web-based application!

----------------------------------------------------------------------------

## Next Steps


----------------------------------------------------------------------------

## Other Resources

**Description** | **URL Link**
--- | ---
My Windows Subsystem for Linux Tutorial | [https://github.com/atet/wsl](https://github.com/atet/wsl?tab=readme-ov-file#atet--wsl)
Ubuntu (through WSL) is Linux-based and MacOS is UNIX-based | <a href="https://learn.microsoft.com/en-us/windows/wsl/compare-versions#:~:text=WSL%202%20is%20the%20current%20default%20version%20when%20installing%20a%20Linux%20distribution%20and%20uses%20the%20latest%20and%20greatest%20in%20virtualization%20technology%20to%20run%20a%20Linux%20kernel%20inside%20of%20a%20lightweight%20utility%20virtual%20machine%20(VM).%20WSL2%20runs%20Linux%20distributions%20as%20isolated%20containers%20inside%20the%20managed%20VM.">WSL: https://learn.microsoft.com/en-us/windows/wsl/compare-versions</a></br></br><a href="https://en.wikipedia.org/wiki/MacOS#:~:text=macOS%2C%20originally%20Mac%20OS%20X,system%20for%20Apple's%20Mac%20computers.">MacOS: https://en.wikipedia.org/wiki/MacOS</a>
Why are people using registries other than Docker Hub? *Docker Hub vs. Quay.io (Red Hat)* | https://www.g2.com/compare/docker-inc-docker-vs-red-hat-quay

[Back to Top](#table-of-contents)

----------------------------------------------------------------------------

## Troubleshooting

Issue | Solution
--- | ---
**"It's not working!"** | This concise tutorial has distilled hours of sweat, tears, and troubleshooting; _it can't not work_

[Back to Top](#atet--python)

----------------------------------------------------------------------------

<p align="center">Copyright © 2025-∞ Athit Kao, <a href="http://www.athitkao.com/tos.html" target="_blank">Terms and Conditions</a></p>