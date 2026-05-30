print("=== AI Prompt Evaluation Toolkit ===")

def evaluate_response(response):
    score = 0

    if len(response) > 50:
        score += 1
    if "because" in response.lower():
        score += 1
    if any(word in response.lower() for word in ["error", "incorrect", "not sure"]):
        score += 1

    return score

prompt = input("Enter a prompt: ")
response1 = input("\nEnter AI Response 1: ")
response2 = input("\nEnter AI Response 2: ")

score1 = evaluate_response(response1)
score2 = evaluate_response(response2)

print("\n=== RESULTS ===")

print("\nResponse 1 Score:", score1)
print("Response 2 Score:", score2)

if score1 > score2:
    print("\nBest Response: Response 1")
elif score2 > score1:
    print("\nBest Response: Response 2")
else:
    print("\nBoth responses are equal quality")
