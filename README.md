# Dados-VTI

## Atividade 1: Mapa Mental

<img width="1600" height="739" alt="image" src="https://github.com/user-attachments/assets/abc95cd1-9531-41d7-bdf9-7cfe25211653" />

## Atividade 2: Apresentação em Equipe
<img width="1170" height="647" alt="image" src="https://github.com/user-attachments/assets/0ba9cf0a-c7f6-4356-a589-1355dbcecb1b" />

## Atividade 3: Manipulação de Dados utilizando o Excel:
<img width="1894" height="713" alt="Captura de tela 2025-09-19 223032" src="https://github.com/user-attachments/assets/6d5c81ee-8134-4fc4-9ab3-2f57792d29f3" />

## Fórmulas Utilizadas para o desenvolvimento da tarefa:
CORRESP,
ÍNDICE,
CONT.SE,
MÁXIMOSES,
MÍNIMOSES,
SOMASES,
CONT.VALORES.

## Atividade 4: Introdução ao Power BI
<img width="1318" height="736" alt="image" src="https://github.com/user-attachments/assets/7b1bd8bf-01f6-45b4-be94-7a022cdb6289" />

## Atividade sobre Regressão Linear:
<img width="1352" height="852" alt="image" src="https://github.com/user-attachments/assets/7b0305a6-8f7f-4d9d-b6a5-012c759d3e3e" />

## Atividade sobre a planilha Sorvete:
{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": [],
      "toc_visible": true,
      "authorship_tag": "ABX9TyNvdC7UM5juXmd1H/mg6+2F",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/KarenVieira5/Dados-VTI/blob/main/AtividadeSorvete.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "Análise de dados sobre sorvete."
      ],
      "metadata": {
        "id": "mOBdE66T16NV"
      }
    },
    {
      "cell_type": "code",
      "execution_count": 4,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "Ngy8cWCR129U",
        "outputId": "ca5ef975-0aaf-43a9-bb84-ea0627ccff21"
      },
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Using Colab cache for faster access to the 'ice-cream-sales-dataset' dataset.\n",
            "Caminho para os arquivos conjuntos de dados: /kaggle/input/ice-cream-sales-dataset\n"
          ]
        }
      ],
      "source": [
        "import kagglehub\n",
        "\n",
        "# Download latest version\n",
        "path = kagglehub.dataset_download(\"sakshisatre/ice-cream-sales-dataset\")\n",
        "\n",
        "print(\"Caminho para os arquivos conjuntos de dados:\", path)"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "import os\n",
        "\n",
        "# Construct the full path to the CSV file\n",
        "csv_path = os.path.join(path, 'Ice Cream.csv')\n",
        "\n",
        "# Read the CSV file into a pandas DataFrame\n",
        "df = pd.read_csv(csv_path)\n",
        "\n",
        "# Display the first few rows of the DataFrame\n",
        "display(df.head(5))"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 206
        },
        "id": "W70ZE4dd5ag9",
        "outputId": "30582cd6-018b-4e1e-9a00-d7f78f718e41"
      },
      "execution_count": 5,
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/plain": [
              "   Temperature  Revenue\n",
              "0         24.6      535\n",
              "1         26.1      626\n",
              "2         27.8      661\n",
              "3         20.6      488\n",
              "4         11.6      317"
            ],
            "text/html": [
              "\n",
              "  <div id=\"df-65b4e3a8-0258-44f3-9a4d-986b9d91b2dc\" class=\"colab-df-container\">\n",
              "    <div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Temperature</th>\n",
              "      <th>Revenue</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>0</th>\n",
              "      <td>24.6</td>\n",
              "      <td>535</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>1</th>\n",
              "      <td>26.1</td>\n",
              "      <td>626</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>2</th>\n",
              "      <td>27.8</td>\n",
              "      <td>661</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>3</th>\n",
              "      <td>20.6</td>\n",
              "      <td>488</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>4</th>\n",
              "      <td>11.6</td>\n",
              "      <td>317</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>\n",
              "    <div class=\"colab-df-buttons\">\n",
              "\n",
              "  <div class=\"colab-df-container\">\n",
              "    <button class=\"colab-df-convert\" onclick=\"convertToInteractive('df-65b4e3a8-0258-44f3-9a4d-986b9d91b2dc')\"\n",
              "            title=\"Convert this dataframe to an interactive table.\"\n",
              "            style=\"display:none;\">\n",
              "\n",
              "  <svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\" viewBox=\"0 -960 960 960\">\n",
              "    <path d=\"M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z\"/>\n",
              "  </svg>\n",
              "    </button>\n",
              "\n",
              "  <style>\n",
              "    .colab-df-container {\n",
              "      display:flex;\n",
              "      gap: 12px;\n",
              "    }\n",
              "\n",
              "    .colab-df-convert {\n",
              "      background-color: #E8F0FE;\n",
              "      border: none;\n",
              "      border-radius: 50%;\n",
              "      cursor: pointer;\n",
              "      display: none;\n",
              "      fill: #1967D2;\n",
              "      height: 32px;\n",
              "      padding: 0 0 0 0;\n",
              "      width: 32px;\n",
              "    }\n",
              "\n",
              "    .colab-df-convert:hover {\n",
              "      background-color: #E2EBFA;\n",
              "      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
              "      fill: #174EA6;\n",
              "    }\n",
              "\n",
              "    .colab-df-buttons div {\n",
              "      margin-bottom: 4px;\n",
              "    }\n",
              "\n",
              "    [theme=dark] .colab-df-convert {\n",
              "      background-color: #3B4455;\n",
              "      fill: #D2E3FC;\n",
              "    }\n",
              "\n",
              "    [theme=dark] .colab-df-convert:hover {\n",
              "      background-color: #434B5C;\n",
              "      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);\n",
              "      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));\n",
              "      fill: #FFFFFF;\n",
              "    }\n",
              "  </style>\n",
              "\n",
              "    <script>\n",
              "      const buttonEl =\n",
              "        document.querySelector('#df-65b4e3a8-0258-44f3-9a4d-986b9d91b2dc button.colab-df-convert');\n",
              "      buttonEl.style.display =\n",
              "        google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
              "\n",
              "      async function convertToInteractive(key) {\n",
              "        const element = document.querySelector('#df-65b4e3a8-0258-44f3-9a4d-986b9d91b2dc');\n",
              "        const dataTable =\n",
              "          await google.colab.kernel.invokeFunction('convertToInteractive',\n",
              "                                                    [key], {});\n",
              "        if (!dataTable) return;\n",
              "\n",
              "        const docLinkHtml = 'Like what you see? Visit the ' +\n",
              "          '<a target=\"_blank\" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'\n",
              "          + ' to learn more about interactive tables.';\n",
              "        element.innerHTML = '';\n",
              "        dataTable['output_type'] = 'display_data';\n",
              "        await google.colab.output.renderOutput(dataTable, element);\n",
              "        const docLink = document.createElement('div');\n",
              "        docLink.innerHTML = docLinkHtml;\n",
              "        element.appendChild(docLink);\n",
              "      }\n",
              "    </script>\n",
              "  </div>\n",
              "\n",
              "\n",
              "    <div id=\"df-0d222bc4-0664-4440-bc15-da8b29aa9dae\">\n",
              "      <button class=\"colab-df-quickchart\" onclick=\"quickchart('df-0d222bc4-0664-4440-bc15-da8b29aa9dae')\"\n",
              "                title=\"Suggest charts\"\n",
              "                style=\"display:none;\">\n",
              "\n",
              "<svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\"viewBox=\"0 0 24 24\"\n",
              "     width=\"24px\">\n",
              "    <g>\n",
              "        <path d=\"M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z\"/>\n",
              "    </g>\n",
              "</svg>\n",
              "      </button>\n",
              "\n",
              "<style>\n",
              "  .colab-df-quickchart {\n",
              "      --bg-color: #E8F0FE;\n",
              "      --fill-color: #1967D2;\n",
              "      --hover-bg-color: #E2EBFA;\n",
              "      --hover-fill-color: #174EA6;\n",
              "      --disabled-fill-color: #AAA;\n",
              "      --disabled-bg-color: #DDD;\n",
              "  }\n",
              "\n",
              "  [theme=dark] .colab-df-quickchart {\n",
              "      --bg-color: #3B4455;\n",
              "      --fill-color: #D2E3FC;\n",
              "      --hover-bg-color: #434B5C;\n",
              "      --hover-fill-color: #FFFFFF;\n",
              "      --disabled-bg-color: #3B4455;\n",
              "      --disabled-fill-color: #666;\n",
              "  }\n",
              "\n",
              "  .colab-df-quickchart {\n",
              "    background-color: var(--bg-color);\n",
              "    border: none;\n",
              "    border-radius: 50%;\n",
              "    cursor: pointer;\n",
              "    display: none;\n",
              "    fill: var(--fill-color);\n",
              "    height: 32px;\n",
              "    padding: 0;\n",
              "    width: 32px;\n",
              "  }\n",
              "\n",
              "  .colab-df-quickchart:hover {\n",
              "    background-color: var(--hover-bg-color);\n",
              "    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
              "    fill: var(--button-hover-fill-color);\n",
              "  }\n",
              "\n",
              "  .colab-df-quickchart-complete:disabled,\n",
              "  .colab-df-quickchart-complete:disabled:hover {\n",
              "    background-color: var(--disabled-bg-color);\n",
              "    fill: var(--disabled-fill-color);\n",
              "    box-shadow: none;\n",
              "  }\n",
              "\n",
              "  .colab-df-spinner {\n",
              "    border: 2px solid var(--fill-color);\n",
              "    border-color: transparent;\n",
              "    border-bottom-color: var(--fill-color);\n",
              "    animation:\n",
              "      spin 1s steps(1) infinite;\n",
              "  }\n",
              "\n",
              "  @keyframes spin {\n",
              "    0% {\n",
              "      border-color: transparent;\n",
              "      border-bottom-color: var(--fill-color);\n",
              "      border-left-color: var(--fill-color);\n",
              "    }\n",
              "    20% {\n",
              "      border-color: transparent;\n",
              "      border-left-color: var(--fill-color);\n",
              "      border-top-color: var(--fill-color);\n",
              "    }\n",
              "    30% {\n",
              "      border-color: transparent;\n",
              "      border-left-color: var(--fill-color);\n",
              "      border-top-color: var(--fill-color);\n",
              "      border-right-color: var(--fill-color);\n",
              "    }\n",
              "    40% {\n",
              "      border-color: transparent;\n",
              "      border-right-color: var(--fill-color);\n",
              "      border-top-color: var(--fill-color);\n",
              "    }\n",
              "    60% {\n",
              "      border-color: transparent;\n",
              "      border-right-color: var(--fill-color);\n",
              "    }\n",
              "    80% {\n",
              "      border-color: transparent;\n",
              "      border-right-color: var(--fill-color);\n",
              "      border-bottom-color: var(--fill-color);\n",
              "    }\n",
              "    90% {\n",
              "      border-color: transparent;\n",
              "      border-bottom-color: var(--fill-color);\n",
              "    }\n",
              "  }\n",
              "</style>\n",
              "\n",
              "      <script>\n",
              "        async function quickchart(key) {\n",
              "          const quickchartButtonEl =\n",
              "            document.querySelector('#' + key + ' button');\n",
              "          quickchartButtonEl.disabled = true;  // To prevent multiple clicks.\n",
              "          quickchartButtonEl.classList.add('colab-df-spinner');\n",
              "          try {\n",
              "            const charts = await google.colab.kernel.invokeFunction(\n",
              "                'suggestCharts', [key], {});\n",
              "          } catch (error) {\n",
              "            console.error('Error during call to suggestCharts:', error);\n",
              "          }\n",
              "          quickchartButtonEl.classList.remove('colab-df-spinner');\n",
              "          quickchartButtonEl.classList.add('colab-df-quickchart-complete');\n",
              "        }\n",
              "        (() => {\n",
              "          let quickchartButtonEl =\n",
              "            document.querySelector('#df-0d222bc4-0664-4440-bc15-da8b29aa9dae button');\n",
              "          quickchartButtonEl.style.display =\n",
              "            google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
              "        })();\n",
              "      </script>\n",
              "    </div>\n",
              "\n",
              "    </div>\n",
              "  </div>\n"
            ],
            "application/vnd.google.colaboratory.intrinsic+json": {
              "type": "dataframe",
              "summary": "{\n  \"name\": \"display(df\",\n  \"rows\": 5,\n  \"fields\": [\n    {\n      \"column\": \"Temperature\",\n      \"properties\": {\n        \"dtype\": \"number\",\n        \"std\": 6.46591060872326,\n        \"min\": 11.6,\n        \"max\": 27.8,\n        \"num_unique_values\": 5,\n        \"samples\": [\n          26.1,\n          11.6,\n          27.8\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    },\n    {\n      \"column\": \"Revenue\",\n      \"properties\": {\n        \"dtype\": \"number\",\n        \"std\": 135,\n        \"min\": 317,\n        \"max\": 661,\n        \"num_unique_values\": 5,\n        \"samples\": [\n          626,\n          317,\n          661\n        ],\n        \"semantic_type\": \"\",\n        \"description\": \"\"\n      }\n    }\n  ]\n}"
            }
          },
          "metadata": {}
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import matplotlib.pyplot as plt\n",
        "import seaborn as sns\n",
        "\n",
        "# Create a scatter plot of Revenue vs Temperature\n",
        "plt.figure(figsize=(10, 6))\n",
        "sns.scatterplot(x='Temperature', y='Revenue', data=df)\n",
        "plt.title('Dispersão de Venda vs Temperatura')\n",
        "plt.xlabel('Temperatura (°C)')\n",
        "plt.ylabel('Venda ()')\n",
        "plt.grid(True)\n",
        "plt.show()"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 550
        },
        "id": "INWqqnzq8tni",
        "outputId": "08611d4a-4451-4a3e-c66f-cfc2d0d57fa8"
      },
      "execution_count": 6,
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/plain": [
              "<Figure size 1000x600 with 1 Axes>"
            ],
            "image/png": "iVBORw0KGgoAAAANSUhEUgAAA1sAAAIjCAYAAAD1OgEdAAAAOnRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjEwLjAsIGh0dHBzOi8vbWF0cGxvdGxpYi5vcmcvlHJYcgAAAAlwSFlzAAAPYQAAD2EBqD+naQAAt1ZJREFUeJzs3Xl4U2X2B/BvmiZp0y0loUChhdJU2SGKbGlBAUUEFcSFiloo4igio/4cBUcQUFHUcRDUYRwFl1HcEBfGDQWFFkSWKru2UCnKUlralDZt1vv7o9xL0qwtXdLy/TzPPEPuvbl5kwbkcM57jkwQBAFERERERETUqMJaegFERERERERtEYMtIiIiIiKiJsBgi4iIiIiIqAkw2CIiIiIiImoCDLaIiIiIiIiaAIMtIiIiIiKiJsBgi4iIiIiIqAkw2CIiIiIiImoCDLaIiIiIiIiaAIMtIiIXCxYsgEwma+llNIrJkycjJiYGDz30EMrKyqDRaFBeXt7kr/vGG29AJpPh999/b/LXakmXX345Lr/88pZeBhERhTAGW0TUZol/6Rf/FxERgcTERIwZMwbLli3DmTNnWnqJTWb//v34/vvvsXDhQnz22WfQarUYPXo0NBpNSy+t3r7//nu3n6NcLkdCQgJuvPFGHDhwoKWXF/LEf0AI9L8LOXDcv38/FixY0Ob/gYCIml94Sy+AiKipLVq0CCkpKbDZbDhx4gS+//573H///XjhhRfw2WefoV+/ftK1jz32GObMmdOCq20c3bt3x86dO9G5c2fcf//9OHHiBDp16tTSyzovs2fPxmWXXQabzYbdu3djxYoV+P7777F371507NixpZcXsm644Qbo9XrpcWVlJe655x5MnDgRN9xwg3S8Q4cOLbG8kLB//34sXLgQl19+Obp169bSyyGiNoTBFhG1eWPHjsXAgQOlx3PnzsWGDRswfvx4XHfddThw4AAiIyMBAOHh4QgPD80/GquqqhAVFRXUtREREejcuTMAICwsDImJiU25tGaRkZGBG2+8UXp88cUX45577sFbb72Fhx9+uAVXFtr69evn9g8KJSUluOeee9CvXz/cdtttLbiyplOf3ysXwjqIqOWwjJCILkgjR47EvHnzcOTIEfz3v/+Vjnvbs7V+/Xqkp6dDo9EgOjoaF198MR599FHpvFjm9v777+PRRx9Fx44dERUVheuuuw5Hjx71eO1t27bh6quvRlxcHNRqNUaMGIHc3Fy3a8R17N+/H7feeivi4+ORnp4OADhx4gSmTZuGLl26QKVSoVOnTrj++uvdSqDWrl2La665BomJiVCpVEhNTcUTTzwBh8PhsZ4PP/wQl156KSIjI6HT6XDbbbfhzz//DOpz3LdvH0aOHInIyEh06dIFTz75JJxOp9drv/zyS2RkZCAqKgoxMTEYN24c9u3bF9TreJORkQEAOHTokNvxP//8E9nZ2ejQoQNUKhV69+6NlStXul0j/sw++OADPPXUU+jSpQsiIiIwatQoFBQUeLzWq6++itTUVERGRmLQoEHYvHmzxzVWqxXz58/HpZdeiri4OERFRSEjIwMbN24M+F7Gjx+P7t27ez03dOhQt38sCPR9bKiDBw/ixhtvRLt27RAREYGBAwfis88+c7tGLM3NycnB7Nmz0b59e2g0GvzlL3+B1WpFeXk57rjjDsTHxyM+Ph4PP/wwBEGQnv/7779DJpPh+eefxz//+U907doVkZGRGDFiBPbu3Xtea/rhhx8wc+ZMJCQkoEuXLgCAI0eOYObMmbj44osRGRkJrVaLm266ye33yhtvvIGbbroJAHDFFVdIZZXff/89AEAmk2HBggUea+vWrRumTp3aaOsgorYpNP/5loioGdx+++149NFH8c0332DGjBler9m3bx/Gjx+Pfv36YdGiRVCpVCgoKPAIjgDgqaeegkwmwyOPPILi4mIsXboUo0ePxs8//yxlzjZs2ICxY8fi0ksvxeOPP46wsDCsWrUKI0eOxObNmzFo0CC3e950001IS0vD4sWLpb+0Tpo0Cfv27cN9992Hbt26obi4GOvXr0dRUZFUArVy5UrExMTgwQcfRFRUFDZu3Ij58+ejoqICzz33nHT/N954A9OmTcNll12Gp59+GidPnsSLL76I3Nxc5OXl+d3jdeLECVxxxRWw2+2YM2cOoqKi8Oqrr0rv1dXbb7+NrKwsjBkzBkuWLIHZbMa//vUvpKenIy8vr0GlW+JfVOPj46VjJ0+exJAhQyCTyTBr1iy0b98eX375JaZPn46Kigrcf//9bvd45plnEBYWhoceeggmkwnPPvsspkyZgm3btknXvP766/jLX/6CYcOG4f7778fhw4dx3XXXoV27dkhKSpKuq6iowGuvvYbMzEzMmDED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73PPPSf84x//EJKSkgSVSiVkZGQIv/zyi8daz2dNglDben/atGmCTqcToqOjhTFjxggHDx70aNsuCILwn//8R+jevbsgl8vdfp84HA7hkUceEXQ6naBWq4UxY8YIBQUFPlu/n+86iKhtkQlCA3auEhGR5Pvvv8cVV1yBDz/8EDfeeGNLL4coZP3+++9ISUnBc889h4ceeqill0NE1OS4Z4uIiIiIiKgJMNgiIiIiIiJqAgy2iIiIiIiImgD3bBERERERETUBZraIiIiIiIiaAIMtIiIiIiKiJsChxkFwOp04duwYYmJiIJPJWno5RERERETUQgRBwJkzZ5CYmIiwMP+5KwZbQTh27BiSkpJaehlERERERBQijh49ii5duvi9hsFWEGJiYgDUfqCxsbEtvBrAZrPhm2++wVVXXQWFQtHSy6E2jt83am78zlFz4veNmhu/c61fRUUFkpKSpBjBHwZbQRBLB2NjY0Mm2FKr1YiNjeVvUmpy/L5Rc+N3jpoTv2/U3PidazuC2V7EBhlERERERERNgMEWERERERFRE2CwRURERERE1AQYbBERERERETUBBltERERERERNgMEWERERERFRE2CwRURERERE1AQYbBERERERETUBBltERERERERNgMEWERERERFRE2CwRURERERE1AQYbBERERERETUBBltERERERERNgMEWERERERFRE2jRYGvTpk249tprkZiYCJlMhk8++cTtvCAImD9/Pjp16oTIyEiMHj0a+fn5btecPn0aU6ZMQWxsLDQaDaZPn47Kykq3a3bv3o2MjAxEREQgKSkJzz77bFO/NSIiIiIiagQmsxWHiiuRV1SGQ6cqYTJbW3pJQWvRYKuqqgr9+/fHyy+/7PX8s88+i2XLlmHFihXYtm0boqKiMGbMGNTU1EjXTJkyBfv27cP69euxbt06bNq0CXfddZd0vqKiAldddRW6du2KnTt34rnnnsOCBQvw6quvNvn7IyIiIiKihjtWXo1Zq/Mw6oUfMPGVLRj1jx9w3+o8HCuvbumlBSW8JV987NixGDt2rNdzgiBg6dKleOyxx3D99dcDAN566y106NABn3zyCSZPnowDBw7gq6++wvbt2zFw4EAAwPLly3HNNdfg+eefR2JiIt555x1YrVasXLkSSqUSvXv3xs8//4wXXnjBLSgjIiIiIqLQYTJb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srKytHTp0kseGwDgAsIWAOCyJCYm2n7FxMQoICDArm3VqlXq27evQkNDddVVV2nJkiW29x47dkwBAQH65z//qZEjRyosLExDhgzRV199pR07dmjw4MGKjIzULbfcojNnztjeN3nyZN1+++2aM2eOunTpoujoaP3nf/6nXXhpaGhQXl6ekpOTFRYWpvT0dL3yyiu26x999JECAgL07rvvatCgQQoJCdGWLVt05MgRjRs3TgkJCYqMjNSQIUP04Ycf2t53/fXX6+uvv9Z9991nW72TpNmzZ2vgwIF2fzbz589Xr169HMb92GOPqVu3burTp48k6X//9381ePBgRUVFKTExURMnTlRRUVGzf+7//Oc/lZ6eriuvvNLWVlZWptjYWKWlpWnQoEGqrq626//SSy9p5cqVeuihhzRkyBD16tVL48aN0/r163XDDTfY+o4dO1arVq1q9vMBAK4Fe3sAAICO66WXXtLMmTO1aNEiZWRkKD8/X/fcc48iIiI0adIkW79Zs2Zp/vz5SkpK0t13362JEycqKipKzz77rMLDw/WTn/xEM2fOtFttWbdunUJDQ/XRRx/p2LFjmjJliuLi4vTYY49JkvLy8vT3v/9dzz33nFJTU7Vp0yb9/Oc/V5cuXXTdddfZ7vPggw/qqaee0ve+9z116tRJx48f1w9/+EM99thjCgkJ0d/+9jeNHTtWBw8eVFJSkl577TWlp6frV7/6le65555W/5msW7dO0dHRWrt2ra2trq5Oc+fOVZ8+fVRUVKTc3FxNnjxZ77zzTpP32bx5swYPHmzX1r9/f6WlpSkmJkZms1l/+ctf7H4Wffr00bhx4xzuFRAQoJiYGNvroUOH6ptvvtGxY8fswiIAoJUMAADayPLly42YmBjb6969exsrVqyw6zN37lwjMzPTMAzDKCgoMCQZzz//vO36ypUrDUnGunXrbG15eXlGnz59bK8nTZpkdO7c2aisrLS1LV261IiMjDTq6+uNmpoaIzw83Pj444/tPnvq1KnGhAkTDMMwjA0bNhiSjNWrV7v8XldffbWxcOFC2+uePXsazzzzjF2fWbNmGenp6XZtzzzzjNGzZ0+7cSckJBi1tbXNft6OHTsMSUZ5eXmTfdLT041HH33U6bXi4mKjqqrKrq1v377Gbbfd1uznWpWWlhqSjI8++qhF/QEAzrGyBQBwi8rKSh05ckRTp061WwE6f/683SqKJKWlpdl+n5CQIEkaMGCAXVvjbXXp6ekKDw+3vc7MzFRFRYWOHz+uiooKVVVV6eabb7Z7j8ViUUZGhl1b49WhiooKzZ49W2+//bZOnjyp8+fPq7q6WoWFha35+k0aMGCAzGazXduuXbs0e/ZsffbZZzp37pwaGhokXXgGq1+/fk7vU11drdDQUKfX4uLiHNoMw2jxGMPCwiTJVjQDAHBpCFsAALeoqKiQdKE63rBhw+yuBQUF2b02mUy231ufgWrcZg0grfnst99+2+6ZJkkKCQmxex0REWH3+v7779fatWv11FNPKSUlRWFhYfrxj3/ssphFYGCgQ6Cpq6tz6Nf48yorK5WVlaWsrCy99NJL6tKliwoLC5WVldXsZ8bHx+vcuXPNjuli3//+9/Xll1+2qO+3334rSerSpUuL7w8AcETYAgC4RUJCgrp166ajR4/qZz/7WZvf/7PPPlN1dbVtFeaTTz5RZGSkevTooc6dOyskJESFhYV2z2e1xNatWzV58mTdcccdki4Et2PHjtn1MZvNqq+vt2vr0qWLTp06JcMwbIFxz549Lj/vyy+/1NmzZzVv3jz16NFDkrRz506X78vIyNCBAwda8I0umDhxon7605/qjTfecHhuyzAMlZWV2VYc9+/fL5PJpKuvvrrF9wcAOKIaIQDAbebMmaO8vDwtWLBAX331lfbt26fly5fr6aefvux7WywWTZ06VQcOHNA777yjWbNmKScnR4GBgYqKitL999+v++67Ty+++KKOHDmi3bt3a+HChXrxxRebvW9qaqpee+017dmzR5999pkmTpzosKrWq1cvbdq0Sf/6179UXFws6UKVwjNnzujJJ5/UkSNHtHjxYr377rsuv0dSUpLMZrMWLlyoo0eP6s0339TcuXNdvi8rK0vbtm1zCH1N+clPfqI777xTEyZM0OOPP66dO3fq66+/1po1azR69Ght2LDB1nfz5s226pAAgEtH2AIAuM0vf/lLPf/881q+fLkGDBig6667Ti+88IKSk5Mv+9433XSTUlNTNWrUKN1555267bbb7A5Qnjt3rh555BHl5eWpb9+++rd/+ze9/fbbLj/76aefVqdOnXTttddq7NixysrK0g9+8AO7Po8++qiOHTum3r1727ba9e3bV0uWLNHixYuVnp6uTz/9tEVnjHXp0kUvvPCCXn75ZfXr10/z5s3TU0895fJ9t9xyi4KDg+3K0jcnICBAK1as0NNPP63Vq1fruuuuU1pammbPnq1x48YpKyvL1nfVqlWXVGkRAGAvwGjNE7MAALQDkydPVklJiVavXu3toXjV4sWL9eabb+r9999vs3u+++67+t3vfqe9e/cqOJinDQDgcvCvKAAAPurXv/61SkpKVF5erqioqDa5Z2VlpZYvX07QAoA2wMoWAMDnsLIFAPAFhC0AAAAAcAMKZAAAAACAGxC2AAAAAMANCFsAAAAA4AaELQAAAABwA8IWAAAAALgBYQsAAAAA3ICwBQAAAABuQNgCAAAAADf4/4VAYXaWqqDzAAAAAElFTkSuQmCC\n"
          },
          "metadata": {}
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "from sklearn.linear_model import LinearRegression\n",
        "from sklearn.model_selection import train_test_split\n",
        "\n",
        "# Prepare the data\n",
        "X = df[['Temperature']]  # Feature (independent variable)\n",
        "y = df['Revenue']      # Target (dependent variable)\n",
        "\n",
        "# Split the data into training and testing sets\n",
        "X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)\n",
        "\n",
        "# Create and train the linear regression model\n",
        "model = LinearRegression()\n",
        "model.fit(X_train, y_train)\n",
        "\n",
        "# Print the model coefficients\n",
        "print(f\"Intercept: {model.intercept_}\")\n",
        "print(f\"Coefficient (Temperature): {model.coef_[0]}\")"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "ve-V-8Wd-qoI",
        "outputId": "0fc14f2c-f729-405c-a64f-81471d87b5f8"
      },
      "execution_count": 7,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Intercept: 46.17834580774047\n",
            "Coefficient (Temperature): 21.384000731002768\n"
          ]
        }
      ]
    }
  ]
}
