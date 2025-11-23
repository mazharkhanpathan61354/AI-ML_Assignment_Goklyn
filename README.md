#CODE USED FOR ML Model Building (Classification Using the Iris Data)
            
            from sklearn.datasets import load_iris
            from sklearn.model_selection import train_test_split
            from sklearn.linear_model import LogisticRegression
            from sklearn.metrics import accuracy_score
            iris = load_iris()
            X = iris.data
            y = iris.target
            X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
            model = LogisticRegression(max_iter=200)
            model.fit(X_train, y_train)
            y_pred = model.predict(X_test)
            print("Model Accuracy:", accuracy_score(y_test, y_pred))


# FOR GRAPH
        import matplotlib.pyplot as plt
        plt.scatter(X[:, 0], X[:, 1], c=y)
        plt.xlabel("Sepal Length")
        plt.ylabel("Sepal Width")
        plt.title("Iris Dataset Visualization")
        plt.show()


# SIMPLE SELF MADE AI AGENT 
    # Task 2: Simple AI Agent
    print("Security Agent started. Type 'exit' to stop.")
    while True:
        user_input = input("You: ").lower()
        if user_input == "exit":
            print("Agent: Bye!")
            break
    
    if "hello" in user_input or "hi" in user_input:
        print("Agent: Hello! I can help with security alerts.")
    
    elif "failed login" in user_input or "password" in user_input:
        print("Agent: That sounds suspicious. You should check the auth logs.")
        print("Agent: If there are many failures, block the IP address.")

    elif "attack" in user_input or "threat" in user_input:
        print("Agent: High alert! Please isolate the affected machine immediately.")

    else:
        print("Agent: I don't understand. Try asking about 'failed login' or 'attacks'.")

