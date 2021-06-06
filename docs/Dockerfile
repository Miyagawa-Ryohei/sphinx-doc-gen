FROM python:3.8.6

WORKDIR /root/

RUN apt update -y && apt install -y \
   texlive-formats-extra \
   texlive-latex-recommended \
   texlive-latex-extra \
   texlive-fonts-recommended \
   texlive-fonts-extra \
   texlive-lang-japanese \
   texlive-lang-cjk \
   latexmk \
   pandoc

RUN pip install poetry

COPY poetry.lock pyproject.toml ./
RUN poetry install
COPY . ./

RUN mkdir build
CMD ["poetry","run","make","html","pdf","markdown"]