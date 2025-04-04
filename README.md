API JATI HE SERVER KE PAS OR REQUEST KRTI HE SERVER SY OR BTATI HE KE ME GET RQUEST HON YA POST YA PUT YA DELETE 
or phir server cheq krta he mery pas is request ke liye konsa response he wo response bhej deta he 

Https ka word jha bhu a jay oska matkb he api ki bat gori he 

jb bhi api bnaty hen fast api to hmy oski documnetation bhi lazmi bnani he jismy hm btaygy ke post put delet me kis trha sy data bhejna he konsi form me bhejna he osky ilawa user ko pta nhi lgyga ke kesy me update delete put kron 

<!-- *********DEPLOYMENY -->

file bana he requirements.tsx ki 
pyproject.tomal me jan he or dependencies me jo jo version hen osko copy krky requiremets.tsx ki file me jakr past krna he version ka number hta dengy 
phir ak file bnaygy vercel.json osmy pas krengy 

""{
  "version": 2,
  "builds": [
    {
      "src": "your_file_name.py",
      "use": "@vercel/python"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "/your_file_name.py"
    }
  ]
}""

file name ki jga apni main.py ka name likhengy

phir githup pr push krengy 

"# FAST_API" 
